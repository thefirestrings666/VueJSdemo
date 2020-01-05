<template>
    <div id="center">
        <div class="starContainer">
            <star-rating :rating-selected="note" @rating-selected="generateChuckFact" :inline="true"></star-rating>
            <div id="container">
                <vue-load-image>
                    <img slot="image" :src='chuckFact' />
                    <img src="static/giphy.gif" slot="preloader" class="loadingLogo" />
                    <div slot="error">image load fails</div>
                </vue-load-image>           
            </div>
        </div>        
    </div>
</template>

<script>
import ChuckFact from "./Chuck"
import axios from "axios"
import VueLoadImage from 'vue-load-image'
import StarRating from 'vue-star-rating'


export default { 

    components: {
        ChuckFact,
        'vue-load-image': VueLoadImage,
        StarRating

    },
    data: () => {
        return {
          chuckFact: "",
          chuckFact2: "",
          note: 0
        }
    },
    created: function () {
        axios.get("https://api.thecatapi.com/v1/images/search").then(response => {
        this.chuckFact =  response.data[0].url
        
        })
    },
    methods: {
        generateChuckFact(noteIn) {
            axios.get("https://api.thecatapi.com/v1/images/search").then(response => {
                this.chuckFact =  response.data[0].url  
            }) 
            this.note = noteIn
            console.log(this.note)
        }
    }

}

</script>

<style>
#center{
    max-width: 800px;
    margin: auto;
}
#container{
    display: grid;
    grid-template-areas: 
        ".";
    padding:  20px 50px 50px 50px; grid-gap: 3.5rem;
    vertical-align: calc(-0.12109375em);
}
.starContainer{
    margin: 20px 0px 00px 0px;
}
img {
  max-width: 800px;
  width: 100%;
}

.img_s {
  width: 100%;
}
.myButton {
	box-shadow:inset 0px 1px 0px 0px #a6827e;
	background:linear-gradient(to bottom, #7d5d3b 5%, #634b30 100%);
	background-color:#7d5d3b;
	border-radius:3px;
	border:1px solid #54381e;
	display:inline-block;
	cursor:pointer;
	color:#ffffff;
	font-family:Arial;
	font-size:13px;
    margin: 40px;
	padding:21px 76px;
	text-decoration:none;
	text-shadow:0px 1px 0px #4d3534;
}
.myButton:hover {
	background:linear-gradient(to bottom, #634b30 5%, #7d5d3b 100%);
	background-color:#634b30;
}
.myButton:active {
	position:relative;
	top:1px;
}

.loadingLogo {
    max-width: 100px;;
}

.bounce { animation: bounce 1s; }

@keyframes bounce {
	  0% { transform: rotate(  0deg) scale(1.0); }
	 33% { transform: rotate( 12deg) scale(1.2); }
	 67% { transform: rotate(-12deg) scale(0.8); }
	100% { transform: rotate(  0deg) scale(1.0); }
}
</style>