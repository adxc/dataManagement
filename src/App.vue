<template>
  <div id="app">
    <z-header></z-header>
    <div class="g-bd">
      <z-slider></z-slider>
      <div class="g-mn">
        <router-view/>
      </div>
    </div>
    <z-footer></z-footer>
  </div>
</template>

<script>
import header from './components/z-header'
import footer from './components/z-footer'
import sliderBar from './components/z-slideBar'
export default {
  name: 'App',
  components: {
    'z-header': header,
    'z-footer': footer,
    'z-slider': sliderBar
  }
}
</script>

<style lang="scss">
@import "./../static/scss/style.scss";
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: flex;
  flex-direction: column;
  height: 100%;
}
.g-bd{
  flex: 1 1 auto;
  display: flex;
}
</style>
