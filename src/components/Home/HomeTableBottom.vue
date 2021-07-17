<template>
  <section class="home-table__bottom">

    <section class="home-table__ls">
      <bar-chart></bar-chart>
    </section>
    <section class="home-table__rs">

      <div class="home-table__item">
        <div class="home-table__item_header double">
          <h3 class="home-table__title">Current plan</h3>
          <a href="#" class="tw-link">View</a>
        </div>
        <div class="home-table__content">{{ dataForPlan.content }}</div>
      </div>

      <div class="home-table__item">
        <div class="home-table__item_header double">
          <h3 class="home-table__title">API keys</h3>
          <a href="#" class="tw-link">View</a>
        </div>
        <div class="home-table__content">{{ dataForApiKeys.content }}</div>
      </div>

    </section>
  </section>
</template>

<script>
  import BarChart from "../Chart/BarChart";

  import {inject} from 'vue'

  export default {
    components: {
      BarChart
    },
    setup() {
      let dataForPlan = inject('homeCurrentPlan')
      let dataForApiKeys = inject('homeApiKeys')

      return {
        dataForPlan,
        dataForApiKeys
      }
    }
  }
</script>

<style scoped>

</style>