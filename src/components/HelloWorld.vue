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
              data: [37, 35, 37, 35, 37, 35, 37, 35, 37, 35, 37, 35, 37, 35, 37, 35],
              fill: false,
              backgroundColor: "transparent",
              borderColor: "red",
              borderDash: [5, 5],
              borderWidth: 1,
              yAxisID: 'y',
            },
            {
              label: 'Humidity',
              data: [100, 25, 100, 25, 50, 10, 10, 10, 50, 25, 100, 25, 100, 25, 100, 25, 100, 25, 100, 25, 100, 25],
              fill: false,
              backgroundColor: "transparent",
              borderColor: "#36495d",
              borderWidth: 1,
              yAxisID: 'y1',
            }
          ]
        },
        chartOptions: {
          scales: {
            yAxes: [
             {
               display: true,
               id: 'y',
               type: 'linear',
               position: 'left',
                ticks: {
                  beginAtZero: true
                        },
                gridLines: {
                display: true,
                            },

               title: {
                 display: true,
                 text: 'Value',
                 color: '#191',
                 font: {
                   family: 'Times',
                   size: 20,
                   style: 'normal',
                   lineHeight: 1.2
                 },
                 padding: {top: 30, left: 0, right: 0, bottom: 0}
               }

            },
              {
                id: 'y1',
                type: 'linear',
                display: true,
                position: 'right',
                ticks: {
                  beginAtZero: true
                },
                gridLines: {
                  display: true,
                  drawOnChartArea: false, // when false, only the grid lines for one axis show up
                }
              }

            ],


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