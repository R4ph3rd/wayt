<template>
  <q-page class="dashboard">
      <v-slider></v-slider>
      <v-timeline></v-timeline>
  </q-page>
</template>

<script>
import Slider from '../components/Slider';
import Timeline from '../components/Timeline';

export default {
  name: 'PageIndex',
  components:{
    'v-slider': Slider,
    'v-timeline': Timeline
  }
}
</script>

<style lang="scss" scoped>
.dashboard{
    // padding-bottom:$footerHeight;

    .timeline{
      $snapshotSize:27vw;
      margin-left:calc(50% - (#{$snapshotSize} /2)); 
      padding-top:20px; 
    }
}
  
</style>
