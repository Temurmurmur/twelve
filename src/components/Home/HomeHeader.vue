<template>
  <div class="home-header">
    <h2 class="home-header__name">Good morning, {{ userName }}</h2>
    <p class="home-header__subtitle">Here whats happening with your Twelve Data account today</p>
  </div>
</template>

<script>
  import {inject} from 'vue'

  export default {
    setup() {
      const userName = inject('userName')

      return {
        userName
      }
    }
  }
</script>

<style scoped>

</style>