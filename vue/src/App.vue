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
  overflow: auto;
  font-family: Arial, sans-serif;
}

#app {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  overflow: visible;
}


#main-content {
  flex: 1;
  overflow-y: auto;
  padding: 20px;
}

</style>
