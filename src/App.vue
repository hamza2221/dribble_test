<template>
  <div id="app">
    <Projects />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Projects from './components/projects/Projects.vue'

export default defineComponent({
  name: 'App',
  components: {
    Projects,
  },
});
</script>

<style lang="scss">
#app {
  font-family: 'Open Sans', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  max-width: 1280px;
  margin: 0 auto;
}
</style>
