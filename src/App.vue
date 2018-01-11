<template>
  <div id="app">
    <Ecard />
  </div>
</template>

<script>
import Ecard from './components/Ecard.vue'

export default {
  name: 'app',
  components: {
    Ecard
  }
}
</script>

<style>
#app {
  position: relative;
  z-index: 0;
  width: 100%;
  background: #F4D5BF url('./assets/apptexture.png') repeat;
  background-size: 10% 30%; 
}
@media screen and (min-width: 1024px){
  #app{
    /*padding: 30px 0;*/
  }
}   
</style>
