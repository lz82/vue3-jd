<template>
  <div class="home-wrapper">
    home
    <tab-bar />
  </div>
</template>

<script>
import TabBar from '@/components/tab-bar';
export default {
  name: 'Home',

  components: {
    TabBar
  }
};
</script>

<style lang="scss">
.home-wrapper {
  font-size: 0.1rem;
}
</style>
