<template>
  <div>
    <button v-on:click="norrisJoke()">Click Me</button>
    <transition name="fade">
      <!--<div class="joke" v-if="currentJoke">{{currentJoke.joke}}</div>-->
      <div class="joke" v-html="currentJoke.joke"></div>
    </transition>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'ChuckNorris',
  data () {
    return {
      currentJoke: null
    }
  },
  methods: {
    norrisJoke () {
      axios.get('https://api.icndb.com/jokes/random').then(response => {
        this.currentJoke = response.data.value
      })
    }
  }
}
</script>

<style scoped>
/* eslint-disable */
button {
  margin-top: 350px;
  -moz-box-shadow: 3px 4px 0px 0px #1564ad;
  -webkit-box-shadow: 3px 4px 0px 0px #1564ad;
  box-shadow: 3px 4px 0px 0px #1564ad;
  background: -webkit-gradient(linear, left top, left bottom, color-st
  (0.05, #79bbff), color-stop(1, #378de5));
  background: -moz-linear-gradient(top, #79bbff 5%, #378de5 100%);
  background: -webkit-linear-gradient(top, #79bbff 5%, #378de5 100%);
  background: -o-linear-gradient(top, #79bbff 5%, #378de5 100%);
  background: -ms-linear-gradient(top, #79bbff 5%, #378de5 100%);
  background: linear-gradient(to bottom, #79bbff 5%, #378de5 100%);
  filter: progid:DXImageTransform.Microsoft.gradie
  (startColorstr='#79bbff', endColorstr='#378de5',GradientType=0);
  background-color: #79bbff;
  -moz-border-radius: 5px;
  -webkit-border-radius: 5px;
  border-radius: 5px;
  border: 1px solid #337bc4;
  display: inline-block;
  cursor: pointer;
  color: #ffffff;
  font-family: Arial;
  font-size: 17px;
  font-weight: bold;
  padding:12px 44px;
  text-decoration: none;
  text-shadow: 0px 1px 0px #528ecc;
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
  background: #edf4fa;
}
</style>
