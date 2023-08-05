<template>
  <div class="about">
    <h1>Generador de frases epicas</h1>
    <broma-p/>
  </div>
</template>
<script>
// @ is an alias to /src
import BromaP from '@/components/BromaP.vue'

export default {
  name: 'AboutView',
  components: {
    BromaP
  }
}
</script>