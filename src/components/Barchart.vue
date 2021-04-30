<script>
import { Pie } from 'vue-chartjs';

export default {
  extends: Pie,
  props: {
    label: {
      type: String,
    },
  },
  // data() {
  //   return {
  //     label: ['Books', 'Magazines', 'Newspapers'],
  //   };
  // },
  mounted() {
    this.gradient = this.$refs.canvas
      .getContext('2d')
      .createLinearGradient(0, 0, 0, 450);
    this.gradient2 = this.$refs.canvas
      .getContext('2d')
      .createLinearGradient(0, 0, 0, 450);

    this.renderChart(
      {
        labels: this.label,
        datasets: [
          {
            backgroundColor: ['orange', '#EF6C01', '#F28A34'],
            data: [75, 12, 13],
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
  color:rgb(255, 193, 77);
  display: flex;
}
</style>
