<template lang="">
  <div class="flex--row justify-end my-card--select" style="margin-bottom:25px;">
    <div class="flex--row my-card--select">
      <div>
        <q-select
          color="grey-3"
          label-color="orange"
          outlined
          v-model="model"
          label="Outlined"
          style="width: 140px;"
        />
      </div>
      <div id="q-app" style="width: 140px !important; margin-left:10px !important;">
        <div class="q">
          <q-input
            outlined v-model="date" mask="####-##-##"
            color="orange">
            <template v-slot:append>
              <q-icon
                name="event" class="cursor-pointer" color="orange">
                <q-popup-proxy
                  ref="qDateProxy"
                  transition-show="scale"
                  transition-hide="scale"
                  style="color:orange;"
                  >
                  <q-date
                    v-model="date"
                    @input="() => $refs.qDateProxy.hide()"
                    style="background:orange;"></q-date>
                </q-popup-proxy>
              </q-icon>
            </template>
          </q-input>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      date: '2021/04/27',
    };
  },
};
</script>
<style lang="scss" scoped>
.my-card {

  &--select {
    display: flex;
    flex-direction: row !important;
    margin-left: 16px;
  }
}
</style>
