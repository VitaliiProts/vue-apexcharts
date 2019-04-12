<template>
  <section id="chart">
    <vue-apex-charts width="500" type="bar" :options="options" :series="series"></vue-apex-charts>
  </section>
</template>

<script>
import VueApexCharts from 'vue-apexcharts';

export default {
  data() {
    return {
      options: {
        chart: {
          id: 'vuechart-example'
        },
        xaxis: {
          categories: [1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998]
        }
      },
      series: [{
        name: 'series-1',
        data: [30, 40, 45, 50, 49, 60, 70, 91]
      }]
    };
  },
  components: { VueApexCharts },
}

</script>
<style scoped></style>
