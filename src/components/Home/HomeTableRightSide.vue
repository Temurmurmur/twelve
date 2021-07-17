<template>
  <section class="home-table__rs">

    <div class="home-table__item">
      <div class="home-table__item_header">
        <div class="home-table__item_img">
          <img src="../../assets/img/info.svg" alt="">
        </div>
        <h3 class="home-table__title">General</h3>
      </div>
      <div class="indicator__row"
           v-for="(item, key) in dataForGeneral"
      >
        <div class="indicator__title">{{ item.title }}</div>
        <div class="indicator__curent">
          <img v-if="item.img" :src="require(`../../assets/img/${item.img}.svg`)" class="flag" alt="">
          {{ item.value }}
        </div>
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
      let dataForGeneral = inject('homeGeneral')

      return {
        dataForGeneral
      }
    }
  }
</script>

<style scoped>

</style>