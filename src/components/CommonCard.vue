<template>
  <q-card>
    {{ title }}
  </q-card>
</template>
<script>
export default {
  props: {
    title: {
      type: String,
      default: '',
    },
  },
};
</script>
<style lang="scss">
</style>
