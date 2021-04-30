<script>
import { Line } from 'vue-chartjs';

export default {
  extends: Line,
  mounted() {
    this.renderChart(
      {
        labels: [
          'Abr 3',
          'Abr 4',
          'Abr 5',
          'Abr 6',
          'Abr 7',
          'Abr 8',
          'Abr 9',
        ],
        datasets: [
          {
            label: 'Faturamento',
            data: [100, 200, 150, 200, 300, 200, 400, 500],
            // turn off to make a gray area
            backgroundColor: 'transparent',
            borderColor: 'orange',
            pointBackgroundColor: 'orange',
            tension: 0,
            borderRadius: 4,
          },
        ],
        options: {
          scales: {
            yAxes: [{
              gridLines: {
                color: 'transparent',
                display: false,
                drawBorder: false,
                zeroLineColor: '#ccc',
                zeroLineWidth: 1,
              },
            }],
          },
        },
      },
      {
        responsive: true,
        maintainAspectRatio: false,
        title: {
          display: false,
        },
      },
    );
  },
};
</script>
<style>

@media screen and (max-width: 800px) {
  canvas {
    width: 300px !important;
  }
}
</style>
