<template lang="">
  <div class="flex my-card--products--title" style="padding:20px 20px 0;">
    <span>{{ containerName }}</span>
    <!-- Select Field -->
    <span>{{ selectField }} <q-icon name="arrow_drop_down"/></span>
  </div>
</template>
<script>
export default {
  props: {
    containerName: {
      type: String,
      default: '',
    },
    selectField: {
      type: String,
      default: '',
    },
  },
};
</script>
<style lang="scss">
.my-card {
   &--protucts {
    &--title {
      padding:20px;

      & > span {
        cursor: pointer;
        color:gray;
      }
    }
  }
}
</style>
