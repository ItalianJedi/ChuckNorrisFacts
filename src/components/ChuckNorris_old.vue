<template>
  <div>
    <button @click="fetchRandomJoke()">Click Me</button>
      <div class="joke" v-if="currentJoke">{{currentJoke.joke}}</div>
      <!--<favorite-jokes v-bind:favoriteJokes="favoriteJokes"></favorite-jokes>-->
  </div>
</template>

<script>
import axios from 'axios';
//import FavoriteJokes from '@/components/FavoriteJokes';


export default {
  name: 'ChuckNorris',
  //components: {
    //'favorite-jokes': FavoriteCities
  //},
  mounted(){
    this.fetchRandomJoke()
  },
  data (){
    return {
      currentJoke: null,
      favoriteJokes: []
    }
  },
  methods: {
    fetchRandomJoke(){
        axios.get('https://api.icndb.com/jokes/random')
        .then(response => {
          this.currentJoke = response.data.value
        })//,
        //saveJoke: function (joke) {
         // this.favoriteJokes.push(joke);
         //this.$ls.set('favoriteJokes', this.favoriteJokes);
        }
    }
  }
//}
</script>

<style scoped>
/*button {
  border: solid;
  font-weight: bold;
  font-size: 30px;
  padding: 10px;
  margin-top: 300px;
}*/

button {
  margin-top: 300px;
-moz-box-shadow: 3px 4px 0px 0px #1564ad;
	-webkit-box-shadow: 3px 4px 0px 0px #1564ad;
	box-shadow: 3px 4px 0px 0px #1564ad;
	background:-webkit-gradient(linear, left top, left bottom, color-stop(0.05, #79bbff), color-stop(1, #378de5));
	background:-moz-linear-gradient(top, #79bbff 5%, #378de5 100%);
	background:-webkit-linear-gradient(top, #79bbff 5%, #378de5 100%);
	background:-o-linear-gradient(top, #79bbff 5%, #378de5 100%);
	background:-ms-linear-gradient(top, #79bbff 5%, #378de5 100%);
	background:linear-gradient(to bottom, #79bbff 5%, #378de5 100%);
	filter:progid:DXImageTransform.Microsoft.gradient(startColorstr='#79bbff', endColorstr='#378de5',GradientType=0);
	background-color:#79bbff;
	-moz-border-radius:5px;
	-webkit-border-radius:5px;
	border-radius:5px;
	border:1px solid #337bc4;
	display:inline-block;
	cursor:pointer;
	color:#ffffff;
	font-family:Arial;
	font-size:17px;
	font-weight:bold;
	padding:12px 44px;
	text-decoration:none;
	text-shadow:0px 1px 0px #528ecc;
}
button:hover {
	background:-webkit-gradient(linear, left top, left bottom, color-stop(0.05, #378de5), color-stop(1, #79bbff));
	background:-moz-linear-gradient(top, #378de5 5%, #79bbff 100%);
	background:-webkit-linear-gradient(top, #378de5 5%, #79bbff 100%);
	background:-o-linear-gradient(top, #378de5 5%, #79bbff 100%);
	background:-ms-linear-gradient(top, #378de5 5%, #79bbff 100%);
	background:linear-gradient(to bottom, #378de5 5%, #79bbff 100%);
	filter:progid:DXImageTransform.Microsoft.gradient(startColorstr='#378de5', endColorstr='#79bbff',GradientType=0);
	background-color:#378de5;
}
button:active {
	position:relative;
	top:1px;
}

.joke {
  font-size: 15px;
  font-weight: bold;
  border: ridge gray;
  width: 350px;
  padding: 10px;
  margin: 60px;
  margin-top: 95px;
  margin-left: auto;
  margin-right: auto;
  background: #EDF4FA;
  -webkit-box-shadow: 0px 3px 0px 2px rgba(0,0,0,0.1), 0px 6px 0px 4px rgba(0,0,0,0.1), 0px 9px 0px 6px rgba(0,0,0,0.1), 0px 12px 0px 8px rgba(0,0,0,0.1), 0px 15px 0px 10px rgba(0,0,0,0.1), 0px 18px 0px 12px rgba(0,0,0,0.1), 0px 21px 0px 14px rgba(0,0,0,0.1), 0px 24px 0px 16px rgba(0,0,0,0.1), 0px 27px 0px 18px rgba(0,0,0,0.1), 0px 30px 0px 20px rgba(0,0,0,0.1), 5px 5px 15px 5px rgba(0,0,0,0); 
  box-shadow: 0px 3px 0px 2px rgba(0,0,0,0.1), 0px 6px 0px 4px rgba(0,0,0,0.1), 0px 9px 0px 6px rgba(0,0,0,0.1), 0px 12px 0px 8px rgba(0,0,0,0.1), 0px 15px 0px 10px rgba(0,0,0,0.1), 0px 18px 0px 12px rgba(0,0,0,0.1), 0px 21px 0px 14px rgba(0,0,0,0.1), 0px 24px 0px 16px rgba(0,0,0,0.1), 0px 27px 0px 18px rgba(0,0,0,0.1), 0px 30px 0px 20px rgba(0,0,0,0.1), 5px 5px 15px 5px rgba(0,0,0,0);
}


</style>
