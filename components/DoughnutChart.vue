
<script>
import { Doughnut } from 'vue-chartjs'

export default {
  extends: Doughnut,
  props: {
    data: {
      type: Object,
      default: null
    }
  },
  mounted () {
    this.renderChart(this.data, {
      responsive: true,
      maintainAspectRatio: true,
      legend: {
        display: false
      },
      cutoutPercentage: 80
    })
  }
}
</script>
