<template>
    <div id="center">
        <div class="starContainer">
            <star-rating @rating-selected="generateNewImage" :inline="true"></star-rating>
            <div>Rating selected : {{ rating }}</div>
            <div id="container">
                <vue-load-image>
                    <img slot="image" :src='imgUrl_1' />
                    <img src="static/giphy.gif" slot="preloader" class="loadingLogo" />
                    <div slot="error">image load fails</div>
                </vue-load-image>           
            </div>
        </div>        
    </div>
</template>

<script>

import imgDisplayer from "./imgLoader"
import axios from "axios"
import VueLoadImage from 'vue-load-image'
import StarRating from 'vue-star-rating'

export default { 

    components: {
        imgDisplayer,
        'vue-load-image': VueLoadImage,
        StarRating
    },
    data: () => {
        return {
          imgUrl_1: "",
          rating: 0
        }
    },
    created: function () {
        axios.get("https://api.thecatapi.com/v1/images/search").then(response => {
        this.imgUrl_1 =  response.data[0].url
        })
    },
    methods: {
        generateNewImage(noteIn) {
            axios.get("https://api.thecatapi.com/v1/images/search").then(response => {
                this.imgUrl_1 =  response.data[0].url  
                this.rating = noteIn;
            }) 
            
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

</style>