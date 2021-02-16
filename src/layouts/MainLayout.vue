<template>
  <q-layout view="lHh Lpr lFf">
    <q-header class="flex justify-center">
      <div class="wayt-logo" ></div>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>

    <q-footer class="flex justify-center items-center">
      <q-btn round color="primary" icon="videocam" size="xl" class="primary-shadow" @click="toggleRecord()"></q-btn>
    </q-footer>

    <q-dialog
            v-model="record"
            persistent
            maximized
            transition-show="slide-up"
            transition-hide="slide-down"
            >
            <img :src="imgSrc" alt="">

            <q-btn color="primary" label="Get Picture" @click="captureImage" />
      </q-dialog>

  </q-layout>
</template>

<script>
import { Plugins, CameraResultType } from '@capacitor/core'
const { Camera } = Plugins;

export default {
  name: 'MainLayout',
  data(){
    return {
      record : false
    }
  },
  methods:{
    toggleRecord(){
      this.record = !this.record;
    },
    async captureImage () {
      const image = await Camera.getPhoto({
        quality: 90,
        allowEditing: true,
        resultType: CameraResultType.Uri
      })
      // image.webPath will contain a path that can be set as an image src.
      // You can access the original file using image.path, which can be
      // passed to the Filesystem API to read the raw data of the image,
      // if desired (or pass resultType: CameraResultType.Base64 to getPhoto)
      this.imageSrc = image.webPath
    }
  }
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
