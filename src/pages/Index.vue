<template>
  <q-page class="flex flex-center">
    <div>
      <q-input
        style="margin-bottom:20px;width:200px;"
        outlined
        color="orange"
        placeholder="Procurar cliente"
      >
        <template v-slot:append>
          <q-icon name="search" />
        </template>
      </q-input>
      <div class="flex--row card">
        <q-card class="card--revenues" style="background:orange;">
          <common-card
            title="Faturamento"
            name-icon="show_chart"
            style="background:orange;color: white;"/>
        </q-card>
        <q-card class="card--customers">
          <common-card
            title="Participantes"
            name-icon="people"
            style="color: black;"/>
        </q-card>
      </div>
      <div>
        <q-card class="my-card">
          <q-card-section class="my-card--main">
          Faturamento diário
          </q-card-section>
        </q-card>
        <q-card class="my-card">
          <q-card-section class="my-card--main--secundary">
          murilo
          </q-card-section>
        </q-card>
      </div>
    </div>
    <q-card-section>
      <Input />
      <q-card class="my-card">
        <q-card-section class="my-card--products">
          <div class="flex my-card--products--title">
            <span>Produtos</span>
            <span style="color:gray;">Mais vendidos <q-icon name="arrow_drop_down"/></span>
          </div>
          <div class="my-card--products--cards">
            <div class="flex">
              <img class="my-card--products--cards--image" src="https://s3-sa-east-1.amazonaws.com/bluesoft-erp/sm3m/ecommerce/produtos/fotos/0b42b32e-52dd-4274-b3e2-8ae9a68ed377/foto_large.jpg"/>
              <div class="my-card--products--cards--itens">
                <b>Coca Cola 350mL</b>
                <span>Quantidade: 35</span>
              </div>
            </div>
          </div>
          <div class="flex my-card--products--score">
            <span>pontos: 150 pts</span>
            <span>resgates: 33 pts</span>
          </div>
        </q-card-section>
      </q-card>
      <q-card class="my-card">
        <q-card-section class="my-card--services">
        Murio
        </q-card-section>
      </q-card>
    </q-card-section>
  </q-page>
</template>

<script>
import CommonCard from 'src/components/CommonCard.vue';
import Input from 'src/components/Input.vue';

export default {
  components: { CommonCard, Input },
  name: 'PageIndex',
  data() {
    return {
      model: null,
      options: [
        'Google', 'Facebook', 'Twitter', 'Apple', 'Oracle',
      ],
    };
  },
};
</script>
<style lang="scss" scoped>
.my-card {

  @media screen and (max-width: 800px) {
    width: 325px;
  }

  &--select {
    // display: flex;
    width:140px;
    margin-left:15px;
    justify-content: end;
    flex-direction: row-reverse;
  }

  &--main {
    width: 500px;
    height: 300px;

    // @media screen and (max-width:600px){
    //   width: 100%;
    // }
    &--secundary {
      margin-top: 15px !important;
      width: 500px;
      height: 210px;
    }
  }

  &--products {
    margin-top: 15px;
    width: 325px;
    height: 430px;

    &--title {
      justify-content: space-between;
    }

    &--cards {
      margin-top: 15px;
      padding: 10px;
      align-items: center;
      height: 60px;
      border: 1px solid rgb(228, 222, 222);
      border-left: 3px solid orange;
      box-shadow: none;
      border-radius: 4px 4px 0px 0px;

      &--itens {
        display: flex;
        flex-direction: column;

        & > b {
          font-size: 12px;
        }

        & > span {
          font-size: 11px;
          font-weight: lighter;
        }
      }

      &--image {
        width: 40px;
        padding-right: 5px;
      }
    }

    &--score {
      padding: 8px;
      border: 1px solid rgb(228, 222, 222);
      border-top:0px;
      border-radius: 0px 0px 4px 4px;
      font-size: 10px;
      justify-content: space-between;
    }
  }

  &--services {
    margin-top: 15px;
    width: 325px;
    height: 190px;
  }
}
.icon-search {
  display:flex;
  flex-direction: end;
}
.card {
  display: flex;
  text-align: center;

  @media screen and (max-width:800px){
    display: flex;
    flex-direction: column;
    width: 100%;

    &--customers {
      margin-left: 0px !important;
    }
  }

  &--revenues,
  &--customers {
    padding: 20px;
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
