<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated class="flex justify-center">
      <div class="wayt-logo" ></div>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>

    <q-footer class="flex justify-center items-center">
      <q-btn round color="primary" icon="videocam" size="xl" class="primary-shadow"></q-btn>
    </q-footer>

  </q-layout>
</template>

<script>
export default {
  name: 'MainLayout',
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

.q-layout{
  padding-left:15px;
  padding-right:15px;
}

.q-page-container{
  padding-bottom:0 !important;
}
</style>
