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
          labels: ['Running', 'Swimming', 'Eating', 'Cycling'],
          datasets: [
            {
              label: 'Human 1',
              data: [20, 10, 4, 2]
            },
            {
              label: 'Human 2',
              data: [10, 20, 2, 4]
            }
          ]
        },
        chartOptions: {
          responsive: false
        }
      }
    }
  },
  mounted () {
    this.renderChart(this.state.chartData, this.state.chartOptions)
  }
})
</script>
