<template>
  <div id="app">
    <the-header />
    <router-view />
    <the-footer />

  </div>
</template>

<script>

import TheHeader from '../src/components/TheHeader.vue';
import TheFooter from '../src/components/TheFooter.vue';



export default {
  components: {
    TheHeader,
    TheFooter,
  }

}
</script>

<style scoped>
html,
body {
  margin: 0;
  padding: 0;
  height: 100%;
  font-family: Arial, sans-serif;
}

#app {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

router-view {
  flex: 1;
  overflow-y: auto;
}

the-footer {
  width: 100%;
  position: relative;
}
</style>
