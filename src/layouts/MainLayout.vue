<template>
  <q-layout view="lHh Lpr lFf">
    <q-header class="flex justify-center">
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
  background:none;

  &::before{
    content: ' ';
    position: absolute;
    z-index:-1;
    left:0;
    width:100%;
    height:40%;

    background: url('../assets/blur.png');

    @supports ((-webkit-backdrop-filter: blur(2em)) or (backdrop-filter: blur(2em))) {
        background: none;
        -webkit-backdrop-filter: blur(10px);
        backdrop-filter: blur(10px);
    }
  }
  
  &::after{
    content: ' ';
    position: absolute;
    z-index:-1;
    left:0;
    width:100%;

    background: $linear-hidding, $linear-hidding;
  }
}

.q-header{
  &::before{
    top:0;
  }

  &::after{
    top:0;
    height:100%;
    transform: rotate(180deg);
  }
}

.q-footer{
  height:$footerHeight;

  &::before{
    top:60%;
  }

  &::after{
    top:0;
    height:100%;
  }

  button{
    transform: translateY(20px);
  }

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
