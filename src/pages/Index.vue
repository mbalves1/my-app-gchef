<template>
  <q-page class="flex flex-center">
    <div>
      <q-input
        v-model="search"
        debounce="500"
        filled
        placeholder="Procurar cliente"
        hint="Debouncing 500ms"
      >
        <template class="icon-search" v-slot:append>
          <q-icon name="search" />
        </template>
      </q-input>
      <div class="flex--row card">
        <div class="card--revenues">
          <CommonCard title="Clientes" />
        </div>
        <div class="card--customers">
          Busted
        </div>
      </div>
      <div>
        <q-card class="my-card">
          <q-card-section class="my-card--main">
          Murio
          </q-card-section>
        </q-card>
        <q-card class="my-card">
          <q-card-section>
          Murio
          </q-card-section>
        </q-card>
      </div>
    </div>
    <div>
      <q-card class="my-card">
        <q-card-section>
        Murio
        </q-card-section>
      </q-card>
      <q-card class="my-card">
        <q-card-section>
        Murio
        </q-card-section>
      </q-card>
      <q-card class="my-card">
        <q-card-section>
        Murio
        </q-card-section>
      </q-card>
    </div>
  </q-page>
</template>

<script>
import CommonCard from '../components/CommonCard';

export default {
  components: [
    CommonCard,
  ],
  name: 'PageIndex',
};
</script>
<style lang="scss" scoped>
.my-card {
  &--main {
    width: 500px;
    height: 500px;

    @media screen and (max-width:600px){
      width: 100%;
    }
  }
}
.icon-search {
  display:flex;
  flex-direction: end;
}
.card {
  display: flex;
  text-align: center;

  &--revenues,
  &--customers {
    padding: 40px;
    margin: 10px 0px 15px;
    width: 100%;
    // border:1px solid black;
    box-shadow: 0 1px 5px rgb(0 0 0 / 20%), 0 2px 2px rgb(0 0 0 / 14%);
    border-radius: 4px;
    vertical-align: top;
    background: #fff;
    position: relative;
  }

  &--customers {
    margin-left: 20px;
  }
}
</style>
