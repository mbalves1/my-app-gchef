<template>
  <q-card :style="styleCommonCard">
    <div class="common-card">
      <q-icon class="common-card--image" :name="nameIcon"/>
      <p class="common-card--text">{{ title }}</p>
    </div>
  </q-card>
</template>
<script>
export default {
  name: 'CommonCard',
  props: {
    title: {
      type: String,
      default: '',
    },
    nameIcon: {
      type: String,
      default: '',
    },
    styleCommonCard: {
      type: String,
      default: '',
    },
  },
};
</script>
<style lang="scss">
.common-card {
  display: flex;

  &--image {
    padding: 10px;
    font-size: 40px;
  }
}
</style>
