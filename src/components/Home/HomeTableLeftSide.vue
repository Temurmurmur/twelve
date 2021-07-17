<template>
  <section class="home-table__ls">
    <div class="home-table__row">

      <div class="home-table__item">
        <div class="home-table__item_header">
          <div class="home-table__item_img">
            <img src="../../assets/img/cloud.svg" alt="">
          </div>
          <h3 class="home-table__title">API</h3>
        </div>
        <indicator
            v-for="(item, idx) in dataForAPI" :key="idx"
            :text="item.title"
            :value="item.value"
            :maxValue="item.maxValue"
        ></indicator>
      </div>

      <div class="home-table__item">
        <div class="home-table__item_header">
          <div class="home-table__item_img">
            <img src="../../assets/img/socket.svg" alt="">
          </div>
          <h3 class="home-table__title">WebSocket</h3>
        </div>
        <indicator
            v-for="(item, idx) in dataForWebsocket" :key="idx"
            :text="item.title"
            :value="item.value"
            :maxValue="item.maxValue"
            :success="item.successAnyway"
        ></indicator>
      </div>

    </div>
  </section>
</template>

<script>
  import indicator from '../indicator'

  import {inject} from 'vue'

  export default {
    components: {
      indicator
    },
    setup() {
      let dataForAPI = inject('homeAPI')
      let dataForWebsocket = inject('homeWebsocket')

      return {
        dataForAPI,
        dataForWebsocket
      }
    }
  }
</script>

<style scoped>

</style>