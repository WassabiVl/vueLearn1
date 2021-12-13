<script>
import { defineComponent } from 'vue'
import { Line } from 'vue3-chart-v2'

export default defineComponent({
  name: 'SportChart',
  extends: Line,
  data () {
    return {
      state: {
        chartData: {
          labels: ['1', '2', '3', '4', '5', '6', '7', '8','9', '10', '11', '12','13', '14', '15', '16'],
          datasets: [
            {
              label: 'Temperature',
              data: [37, 35, 37, 35, 37, 35, 37, 35, 37, 35, 37, 35, 37, 35, 37, 35, 37, 35, 37, 35, 37, 35, 37, 35],
              fill: false,
              backgroundColor: "transparent",
              borderColor: "red",
              borderWidth: 1
            },
            {
              label: 'Humidity',
              data: [100, 25, 100, 25, 100, 25, 100, 25, 100, 25, 100, 25, 100, 25, 100, 25, 100, 25, 100, 25, 100, 25],
              backgroundColor: "transparent",
              borderColor: "#36495d",
              fill: false,
              borderWidth: 1
            }
          ]
        },
        chartOptions: {
          scales: {
            yAxes: [{
              ticks: {
                beginAtZero: true
              },
              gridLines: {
                display: true
              }
            }],
            xAxes: [ {
              gridLines: {
                display: false
              }
            }]
          },

          responsive: true,
          maintainAspectRatio: false
        }
      }
     }
 },
  mounted () {
    this.renderChart(this.state.chartData, this.state.chartOptions)
  }
   })
</script>