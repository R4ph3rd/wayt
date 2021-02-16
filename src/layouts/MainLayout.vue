<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <div class="wayt-logo"></div>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>

  </q-layout>
</template>

<script>
export default {
  name: 'MainLayout',
}
</script>

<style lang="scss" scoped>
  
</style>
