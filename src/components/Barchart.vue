<script>
import { Pie } from 'vue-chartjs';

export default {
  extends: Pie,
  mounted() {
    this.gradient = this.$refs.canvas
      .getContext('2d')
      .createLinearGradient(0, 0, 0, 450);
    this.gradient2 = this.$refs.canvas
      .getContext('2d')
      .createLinearGradient(0, 0, 0, 450);

    this.gradient.addColorStop(0, 'rgba(255, 140, 0, 0.5)');
    this.gradient.addColorStop(0.5, 'rgba(255, 140, 0, 0.25)');
    this.gradient.addColorStop(1, 'rgba(255, 140, 0, 0)');

    this.gradient2.addColorStop(0, 'rgba(255, 69, 0, 0.9)');
    this.gradient2.addColorStop(0.5, 'rgba(255, 69, 0, 0.25)');
    this.gradient2.addColorStop(1, 'rgba(255, 69, 0, 0)');
    this.renderChart(
      {
        labels: ['Books', 'Magazines', 'Newspapers'],
        datasets: [
          {
            backgroundColor: [this.gradient, this.gradient2, '#FF8C00'],
            data: [40, 20, 10],
          },
        ],
      },
      { responsive: true, maintainAspectRatio: false },
    );
  },
};
</script>
<style>
canvas {
    color:orange;
    display: flex;
}
</style>
