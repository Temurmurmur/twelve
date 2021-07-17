<template>
  <article class="main">
    <sidebar></sidebar>
    <home></home>
  </article>
</template>

<script>
  import Home from "./components/Home/Home";
  import Sidebar from "./components/Sidebar/Sidebar"
  import {provide, ref} from 'vue'

  export default {
    components: {
      Home,
      Sidebar
    },
    setup() {
      const user = ref({
        name: 'Nicholas'
      })
      const homeAPI = [
        {
          title: 'Total requests',
          value: '17,054',
          maxValue: 'infinite' // что бы отображался знак бесконечности
        },
        {
          title: 'Average per minute',
          value: '377',
          maxValue: '610'
        },
        {
          title: 'Average per minute',
          value: '869',
          maxValue: '610'
        }
      ]

      const homeWebsocket = [
        {
          title: 'Connections used',
          value: '2',
          maxValue: '3',
          successAnyway: true
        },
        {
          title: 'Current subscriptions',
          value: '432',
          maxValue: '500'
        }
      ]

      const homeGeneral = [
        {
          title: 'Top symbol',
          value: 'AAPL',
        },
        {
          title: 'Top country',
          value: 'USA',
          img: 'usa'
        },
        {
          title: 'Top exchange',
          value: 'NASDAQ',
        },
      ]

      const homeCurrentPlan = {
        content: 'Pro 610'
      }

      const homeApiKeys = {
        content: '20af0d257cc949c29e41d8aa2664a268'
      }

      const resourcesLinks = [
        {
          title: 'Getting started (basics)',
          link: '#'
        },
        {
          title: 'WebSocket FAQ',
          link: 'https://websockets.readthedocs.io/en/stable/faq.html'
        },
        {
          title: 'Trial',
          link: '#'
        },
        {
          title: 'Excel Add-in docs',
          link: 'https://docs.microsoft.com/ru-ru/office/dev/add-ins/excel/'
        },
        {
          title: 'Python manual',
          link: 'https://docs.python.org/3/'
        }
      ]

      const resourcesApiPlayground = {
        content: 'Descriprion'
      }

      const resourcesWebSocketPlayground = {
        content: 'Descriprion'
      }

      const resourcesSupportCenter = {
        content: 'Descriprion'
      }

      const resourcesAddOns = {
        content: 'Descriprion'
      }


      provide('userName', user.value.name)
      provide('homeAPI', homeAPI)
      provide('homeWebsocket', homeWebsocket)
      provide('homeGeneral', homeGeneral)
      provide('homeApiKeys', homeApiKeys)
      provide('homeCurrentPlan', homeCurrentPlan)

      provide('resourcesLinks', resourcesLinks)
      provide('resourcesApiPlayground', resourcesApiPlayground)
      provide('resourcesWebSocketPlayground', resourcesWebSocketPlayground)
      provide('resourcesSupportCenter', resourcesSupportCenter)
      provide('resourcesAddOns', resourcesAddOns)

      return {}
    }
  }
</script>

<style lang="scss">
  @import "assets/scss/styles";
</style>
