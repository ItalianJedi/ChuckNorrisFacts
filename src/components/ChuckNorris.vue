<template>
  <div>
    <button v-on:click="norrisJoke()">Click Me</button>
    <div class="joke" v-if="currentJoke">{{currentJoke.joke}}</div>
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
