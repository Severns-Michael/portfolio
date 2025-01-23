<template>
  <div id="capstone-app">
    <the-header />
    <router-view />
    <the-footer />
    <terminal-page />
  </div>
</template>

<script>

import TheHeader from '../src/components/TheHeader.vue';
import TheFooter from '../src/components/TheFooter.vue';
import TerminalPage from './components/TerminalPage.vue';


export default {
  components: {
    TheHeader,
    TheFooter,
    TerminalPage,
  }

}
</script>

<style>

</style>
