<template>
  <div>
    <Bar ref="chart" :data="chartData" :options="chartOptions" />
  </div>
</template>

<script>
import { Bar } from 'vue-chartjs'
import { Chart as ChartJS, Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale } from 'chart.js'

ChartJS.register(Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale)

export default {
  name: 'BarChart',
  components: { Bar },
  data() {
    return {
      chartData: {
          labels: ['1', '2', '3', '4', '5', '6', '7', '8'],
          datasets: [{
            data: [24, 20, 12, 35, 25, 12, 16, 23], 
            backgroundColor: 'blue',
            borderRadius: 12,
          }]
        },
      chartOptions: {
        scales: {
          x: {
            grid: {
              display: false, 
            },
            ticks: {
              display: false, 
            },
            categoryPercentage: 0.4,
            barPercentage: 0.5,
          },
          y: {
            grid: {
              display: false, 
            },
            ticks: {
              display: false,
            }
          }
        },
        maintainAspectRatio: true,
        aspectRatio: 2,
        plugins: {
        legend: {
          display: false 
        }
      }
      },
    };
  },
  methods: {
    updateChartOptions() {
      if (window.innerWidth <= 375) {
        this.chartOptions.maintainAspectRatio = true;
        this.chartOptions.aspectRatio = 1;
      } else {
        this.chartOptions.maintainAspectRatio = true;
        this.chartOptions.aspectRatio = 2;
      }
    }
  },
  mounted() {
    this.updateChartOptions(); 
    window.addEventListener('resize', this.updateChartOptions);
  },
  beforeUnmount() {
  window.removeEventListener('resize', this.updateChartOptions);
}
}
</script>