<template>
  <section class="chart">
    <apexchart
        width="100%"
        height="250px"
        type="area"
        :options="chartOptions"
        :series="series"
    ></apexchart>
  </section>
</template>

<script>
  export default {
    data: function () {
      return {
        chartOptions: {
          chart: {
            id: "vuechart-example",
          },
          xaxis: {
            categories: ['12:00am', '01:00pm', '02:00pm', '03:00pm', '04:00pm', '05:00pm', '06:00pm'],
          },
        },
        series: [
          {
            name: "series-1",
            data: [30, 40, 35, 120, 70, 60, 90, 20],
          },
        ],
      };
    },
  };
</script>

<style scoped>

</style>