
<script>
import { Bar } from 'vue-chartjs'

export default {
  extends: Bar,
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
      }
    })
  }
}
</script>
