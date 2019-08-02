<template>
  <div id="app">
    <header class="header">
      <div class="text=box">
        <h1 class="heading-primary">
          <span class="heading-primary-main">Chuck Norris Facts!</span>
        </h1>
        <chuck-norris/>
      </div>
    </header>
  </div>
</template>

<script>
import ChuckNorris from './components/ChuckNorris'

export default {
  name: 'App',
  components: {
    ChuckNorris
  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.heading-primary-main {
  font-family: 'Londrina Shadow', cursive;
  font-size: 80px;
  color: #393C3F;
  font-weight: bold;
  position: absolute;
  top: 30%;
  left: 50%;
  transform: translate(-50%, -50%);
}

body {
  background: #4F5051;
  padding: 30px;
}

.header {
  height: 95vh;
  background-image: linear-gradient(
    to right bottom,
    rgba(110, 179, 239, 0.795),
    rgba(43, 104, 158, 0.808))
    , url(./assets/chuck_norris.jpg);
  background-repeat: no-repeat;
  background-position: top;
  clip-path: polygon(0 0, 100% 0, 100% 80%, 0 100%)
}

.text-box {
  position: absolute;
  top: 50%;
  left: 50%;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /*margin-top: 15px;*/
}
</style>
