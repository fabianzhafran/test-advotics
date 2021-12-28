<script>
import { Bar } from 'vue-chartjs'

export default {
  extends: Bar,
  mounted () {
    this.renderChart({
      labels: ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday', 'Sunday'],
      datasets: [
        {
          type: 'line',
          label: 'Line',
          backgroundColor: '#FFE854',
          fill: false,
          data: [350, 300, 100, 1020, 300, 350, 600]
        },
        {
          type: 'bar',
          label: 'Gross',
          backgroundColor: '#12c44c',
          data: [1050, 900, 1000, 300, 400, 420, 700]
        },
        {
          type: 'bar',
          label: 'Nett',
          backgroundColor: '#6BE681',
          data: [400, 600, 500, 700, 700, 900, 1000]
        },
        {
          type: 'bar',
          label: 'Average Purchase Value',
          backgroundColor: '#289E45',
          data: [200, 400, 600, 900, 1200, 700, 900]
        },
        {
          type: 'bar',
          label: 'Unit Transaction',
          backgroundColor: '#3c7c3a',
          data: [100, 900, 300, 1200, 1400, 300, 500]
        }
      ]}, {
        title: {
          display: true,
          text: 'Oversikt'
        },
        scales: {
          yAxes: [{
            stacked: true
          }],
          xAxes: [ {
            stacked: true,
            categoryPercentage: 0.5,
            barPercentage: 1
          }]
        },
        legend: {
          display: true
        },
        responsive: true,
        maintainAspectRatio: false
      }
    )
  }
}
</script>