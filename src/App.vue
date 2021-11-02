<template>
  <div id="app">
      <PageLayout  />
  </div>
</template>

<script>
import PageLayout from "./components/page/PageLayout";

export default {
  name: 'App',
  components: {
      PageLayout
  },
}
</script>

<style lang="scss">
@import './assets/scss/main';
</style>
