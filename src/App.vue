<template>
  <div class="app">
    app
    <home />
  </div>
</template>

<script>
import Home from '@/views/home';
export default {
  name: 'App',

  components: {
    Home
  }
};
</script>

<style lang="scss">
.app {
  font-size: 0.1rem;
}
</style>
