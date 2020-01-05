<template>
    <div id=center>
        <h1>Hello !</h1>
        <chuck-fact :fact="chuckFact" />
        <div>
            <button class="myButton" @click="generateChuckFact()"><img class="img_s" src="https://cdn.shopify.com/s/files/1/1061/1924/products/Happy_cat_emoji_icon_87ab6b39-5f08-48a5-a89a-1f5d3312e159_large.png"/></button>
        </div>
    </div>
</template>

<script>
import ChuckFact from "./Chuck"
import axios from "axios"


export default { 

    components: {
        ChuckFact,

    },
    data: () => {
        return {
          chuckFact: ""
        }
    },
    methods: {
        generateChuckFact() {
            axios.get("https://api.thecatapi.com/v1/images/search").then(response => {
                this.chuckFact =  response.data[0].url
                console.log(this.chuckFact)  
            })
        }
    }
}

</script>

<style>
img {
  width: 90%;
}

.img_s {
  width: 20%;
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

</style>