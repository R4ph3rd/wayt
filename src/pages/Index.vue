<template>
  <q-page class="flex flex-center">
      <v-slider></v-slider>
  </q-page>
</template>

<script>
import Slider from '../components/Slider';

export default {
  name: 'PageIndex',
  components:{
    'v-slider': Slider
  }
}
</script>
