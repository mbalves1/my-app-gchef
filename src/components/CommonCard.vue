<template>
  <q-card :style="styleCommonCard">
    <div class="common-card">
      <q-icon class="common-card--image" :name="nameIcon"/>
      <div class="common-card--container">
        <p class="common-card--text">{{ title }}</p>
        <span class="common-card--span">{{ numberChoose }}</span>
      </div>
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
    numberChoose: {
      type: Function,
      default: () => {},
    },
  },
};
</script>
<style lang="scss">
.common-card {
  display: flex;

  &--container {
    justify-content: center;
    align-items: center;
    flex-direction: column;
    display: flex;
  }

  &--image {
    padding: 10px;
    font-size: 40px;
    margin-right: 10px;
  }

  &--text {
    padding: 0px !important;
    margin-bottom: 0px !important;
    font-weight: bold;
    font-size: 14px;
  }

  &--span {
    font-size: 18px;
    font-weight: bold;
  }
}
</style>
