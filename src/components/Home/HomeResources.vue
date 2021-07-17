<template>
  <section class="resources">
    <h2 class="title-h2 resources__h2">Resources</h2>

    <div class="resources__table">
      <div class="resources__col">
        <div class="resources__item">
          <a class="resources__link"
             v-for="(item, idx) in dataForResourcesLinks"
             :key="idx"
             :href="item.link"
          >
            <img src="../../assets/img/lnk.svg" alt="">{{ item.title }}
          </a>
        </div>
      </div>
      <div class="resources__col">

        <div class="resources__item">
          <div class="home-table__item_header double">
            <h3 class="home-table__title">API playground</h3>
            <a href="#" class="tw-link">View</a>
          </div>
          <div class="home-table__content">{{ resourcesApiPlayground.content }}</div>
        </div>

        <div class="resources__item">
          <div class="home-table__item_header double">
            <h3 class="home-table__title">WebSocket playground</h3>
            <a href="#" class="tw-link">View</a>
          </div>
          <div class="home-table__content">{{ resourcesWebSocketPlayground.content }}</div>
        </div>

      </div>
      <div class="resources__col">

        <div class="resources__item">
          <div class="home-table__item_header double">
            <h3 class="home-table__title">Support center</h3>
            <a href="#" class="tw-link">View</a>
          </div>
          <div class="home-table__content">{{ resourcesSupportCenter.content }}</div>
        </div>

        <div class="resources__item">
          <div class="home-table__item_header double">
            <h3 class="home-table__title">Add-ons</h3>
            <a href="#" class="tw-link">View</a>
          </div>
          <div class="home-table__content">{{ resourcesAddOns.content }}</div>
        </div>

      </div>
    </div>
  </section>
</template>

<script>


  import {inject} from 'vue'

  export default {
    components: {},
    setup() {
      let dataForResourcesLinks = inject('resourcesLinks')
      let resourcesApiPlayground = inject('resourcesApiPlayground')
      let resourcesWebSocketPlayground = inject('resourcesWebSocketPlayground')
      let resourcesSupportCenter = inject('resourcesSupportCenter')
      let resourcesAddOns = inject('resourcesAddOns')

      return {
        dataForResourcesLinks,
        resourcesApiPlayground,
        resourcesWebSocketPlayground,
        resourcesSupportCenter,
        resourcesAddOns
      }
    }
  }
</script>

<style scoped>

</style>