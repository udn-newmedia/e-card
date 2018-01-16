<template>
  <div id="app" :style="{backgroundImage: 'url('+ apptexture +')'}">
    <Ecard />
  </div>
</template>

<script>
import Ecard from './components/Ecard.vue'

import apptexture from './assets/apptexture.png'

export default {
  name: 'app',
  components: {
    Ecard
  },
  data: function() {
    return {
      apptexture: apptexture,
    }
  },
}
</script>

<style>
#app {
  position: relative;
  z-index: 0;
  width: 100%;
  background: #F4D5BF repeat;
  background-size: 10% 30%; 
}
@media screen and (min-width: 1024px){
  #app{
    /*padding: 30px 0;*/
  }
}   
</style>
