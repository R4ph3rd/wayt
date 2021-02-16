<template>
  <q-layout view="lHh Lpr lFf">

    <q-page-container>
      <router-view />
    </q-page-container>


  </q-layout>
</template>

<script>
export default {
  name: 'ViewLayout',
}
</script>

<style lang="scss" scoped>
.q-header, .q-footer{
  background: rgb(255,255,255, .7);
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
}

.q-footer{
  height:16vh;

  /* & .q-btn{
    display:block;
  } */
}
</style>
