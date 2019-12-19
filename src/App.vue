<template>
  <div id="app">
    <Flexbox />
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import Flexbox from '@/components/Flexbox.vue';

export default Vue.extend({
  name: 'app',
  components: {
    Flexbox
  }
});
</script>

<style>
#app {
  font-family: 'Open Sans', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
</style>
