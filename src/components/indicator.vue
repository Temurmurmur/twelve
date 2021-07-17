<template>
  <div class="indicator">
    <div class="indicator__row">
      <div class="indicator__title">{{ title }}</div>
      <div class="indicator__curent">
        <span class="indicator__val"
              :class="setLineColor.textColor"
        >
          {{ indicateValue }}
        </span> /
        <img src="../assets/img/infinite.svg" v-if="indicateMaxValue == 'infinite'" alt="">
        <span class="indicator__max" v-else>{{ indicateMaxValue }}</span>
      </div>
    </div>
    <div class="indicator__line-wrap" :class="setLineColor.indicatorColor">
      <div class="indicator__line" :style="{ width: countPercent + '%' }"></div>
    </div>
  </div>
</template>

<script>

  import {ref, computed} from 'vue'

  export default {
    props: ['value', 'maxValue', 'text', 'success'],
    setup(props) {
      let title = ref(props.text)
      let indicateValue = ref(props.value) // левое значение
      let indicateMaxValue = ref(props.maxValue) // правое значение
      let successAnyway = ref(props.success)
      let textColor = ref('')
      let indicatorColor = ref('')

      // SetLineColor задает цвет полосе и цифровому значению, в зависимости от процентного промежутка
      const setLineColor = computed(() => {

        if (indicateMaxValue.value == 'infinite' || successAnyway.value) {
          return {indicatorColor: 'indicator__few', textColor: 'success'}
        }

        if (countPercent.value <= 40) {
          textColor = ref('success')
          indicatorColor = ref('indicator__few')
        } else if (countPercent.value <= 70) {
          textColor = ref('warn')
          indicatorColor = ref('indicator__mean')
        } else if (countPercent.value > 70) {
          textColor = ref('danger')
          indicatorColor = ref('indicator__high')
        }

        return {indicatorColor: indicatorColor.value, textColor: textColor.value}
      })

      // Высчитывает процентное соотношение
      const countPercent = computed(() => {
        if (indicateMaxValue.value == 'infinite') {
          return 100
        }
        return (Number(indicateValue.value) * 100) / Number(indicateMaxValue.value)
      })

      return {
        indicateValue,
        indicateMaxValue,
        setLineColor,
        countPercent,
        textColor,
        title
      }
    }
  }
</script>

<style scoped>

</style>