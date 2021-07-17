<template>
  <div class="home indent">
    <home-header></home-header>

    <!-- API WebSocket General -->
    <section class="home-table">

      <home-table-left-side></home-table-left-side>

      <!-- General -->
      <home-table-right-side></home-table-right-side>

    </section>
    <!-- end API WebSocket General-->

    <home-table-bottom></home-table-bottom>
    <!-- END TOP TABLE -->


    <!-- RESOURCES -->
    <home-resources></home-resources>
  </div>
</template>

<script>
  import HomeHeader from "./HomeHeader";
  import HomeTableLeftSide from "./HomeTableLeftSide";
  import HomeTableRightSide from "./HomeTableRightSide";
  import HomeTableBottom from "./HomeTableBottom";
  import HomeResources from "./HomeResources";

  import {inject} from 'vue'


  export default {
    components: {
      HomeHeader,
      HomeTableLeftSide,
      HomeTableRightSide,
      HomeTableBottom,
      HomeResources
    },
    setup() {


      return {}
    }
  }
</script>

<style scoped>

</style>