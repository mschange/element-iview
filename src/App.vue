<template>
  <div>
    <!-- element-ui左边导航栏 -->
    <slider-tree></slider-tree>
    <!-- iview-ui左侧导航栏 -->
    <iview-slider></iview-slider>
  </div>
</template>
<script>
import sliderTree from './components/tree'
import iviewSlider from './components/iveiew/side-menu.vue'
export default {
  components: {
    'slider-tree': sliderTree,
    'iview-slider': iviewSlider
  },
  data() {
    return {}
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
