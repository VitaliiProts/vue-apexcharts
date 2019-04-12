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
        // Параметри самих колонок
        plotOptions: {
          bar: {
            horizontal: false,
            columnWidth: '20%',
            endingShape: 'rounded',
            colors: {
            ranges: [{
                from: 0,
                to: 0,
                color: undefined
            }],
            backgroundBarColors: ['#666'],
            backgroundBarOpacity: 0.3,
            },
            dataLabels: {
            position: 'left',
            }
          },
        },
        // кастомізація даних по X
        xaxis: {
        categories: [123, 234, 345, 567, 678],
        maxWidth: 200,
        labels: {
            show: true,
            rotate: -45,
            rotateAlways: false,
            hideOverlappingLabels: false, // ця опція запобігає накладанню лейблів (коли лейбл дуже близько один до одного)
            trim: true,
            minHeight: undefined,
            maxHeight: 150,
            style: {
                colors: [],
                fontSize: '12px',
                fontFamily: 'Helvetica, Arial, sans-serif',
                cssClass: 'apexcharts-xaxis-label',
            },
            offsetX: 0,
            offsetY: 0,
            format: undefined, // для дати (https://apexcharts.com/docs/datetime/)
            formatter: (e) => {
              return e + '%';
            },
        },
        axisTicks: {
            show: true,
            borderType: 'solid',
            color: '#78909C',
            height: 6,
            offsetX: 0,
            offsetY: 0
        },
        position: 'bottom',
        title: {
            text: 'This is some title',
            offsetX: 0,
            offsetY: 0,
            style: {
                color: [],
                fontSize: '24px',
                fontFamily: 'Helvetica, Arial, sans-serif',
                cssClass: 'apexcharts-xaxis-title',
            },
        },
        // При наведенні на чарт
        crosshairs: {
            show: false,
            width: 12,
            position: 'back',
            opacity: 0.9,        
            stroke: {
                color: '#b6b6b6',
                width: 0,
                dashArray: 0,
            },
            fill: {
                type: 'solid',
                color: '#B1B9C4',
                gradient: {
                    colorFrom: '#D8E3F0',
                    colorTo: '#BED1E6',
                    stops: [0, 100],
                    opacityFrom: 0.4,
                    opacityTo: 0.5,
                },
            },
            dropShadow: {
                enabled: false,
                top: 0,
                left: 0,
                blur: 1,
                opacity: 0.4,
            },
        },
        tooltip: {
            enabled: false,
            formatter: undefined,
            offsetY: 0,
        },
    }
      },
      series: [
        {
          name: 'series-1',
          data: [30, 40, 45, 50, 49]
        },
      ]
    };
  },
  components: { VueApexCharts },
}

</script>
<style scoped></style>
