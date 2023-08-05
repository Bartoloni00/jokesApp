<template>
  <div class="home">
    <HelloWorld msg="Generador de frases epicas"/>
  </div>
</template>
<style scoped>
  .home{
    width: 100vw;
    height: 100%;
    background: #1A183E;
background: radial-gradient(at center bottom, #0c0a2c, #051424);
    background-image: url("../assets/home-back.jpg");
    background-repeat: no-repeat;
  }
</style>
<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  }
}
</script>
