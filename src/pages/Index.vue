<template>
  <q-page class="flex flex-center">
    <div>
      <q-input
        class="first-input"
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
            style="background:orange;color: white;"
            :numberChoose="cash ? 'R$ 300,00' : '100Clientes'"
            cash="300"
          />
        </q-card>
        <q-card class="card--customers">
          <common-card
            title="Participantes"
            name-icon="people"
            style="color: black;"
            :numberChoose="!cash ? 'R$ 300,00' : '100 Clientes'"
          />
        </q-card>
      </div>
      <div>
        <q-card class="my-card">
          <q-card-section class="my-card--main">
            Faturamento diário
            <div>
              <Line-chart
                class="linechart"
                style="width: 464px !important; height: 250px !important;" />
            </div>
          </q-card-section>
        </q-card>
        <q-card class="my-card">
          <q-card-section class="my-card--main--secundary">
            <div class="flex"
              style="
              display:flex;
              justify-content:center;"
            >
              <Barchart
                style="width: 150px !important;
                height: 150px !important;
                display:flex;
                justify-content:center;" />
            </div>
          </q-card-section>
        </q-card>
      </div>
    </div>
    <q-card-section style="margin-left:5px;">
      <Input />
      <q-card class="my-card">
        <Basics-titles container-name="Produtos" select-field="Mais Vendidos" />
        <q-card-section class="my-card--products">
          <products
            product="Coca Cola 350mL"
            amount="35"
            normal-price="3,50"
            promotionPrice="2,99"
            points="150"
            redeem-points="33"
            image-src="https://s3-sa-east-1.amazonaws.com/bluesoft-erp/sm3m/ecommerce/produtos/fotos/0b42b32e-52dd-4274-b3e2-8ae9a68ed377/foto_large.jpg"
          />
          <products
            product="X-Burguer"
            amount="55"
            normal-price="42,35"
            promotionPrice="40,00"
            points="120"
            redeem-points="20"
            image-src="https://admin.cmpedidos.com.br/foto/567/produtos/x-egg-73519.jpg"
          />
          <products
            product="Espeto de Carne"
            amount="80"
            normal-price="4,50"
            promotionPrice="3,50"
            points=""
            redeem-points=""
            image-src="https://www.kispeto.com.br/site/wp-content/uploads/2017/03/espetinho-de-carne-min.png"
            :havePoint="false"
          />
        </q-card-section>
      </q-card>
      <q-card class="my-card">
        <q-card-section class="my-card--services">
          <Basics-titles
            container-name="Serviços"
            select-field="Mais Utilizados"
            style="padding: 2px 6px 0px;"
          />
          <div class="flex my-card--services--box">
            <b>Permite cobrar taxa de entrega de pedidos</b>
            <span>Quantidade: 33 - R$ 20,00 em média</span>
          </div>
        </q-card-section>
      </q-card>
    </q-card-section>
  </q-page>
</template>

<script>
import CommonCard from 'src/components/CommonCard.vue';
import Input from 'src/components/Input.vue';
import Products from 'src/components/Products.vue';
import BasicsTitles from 'src/components/basicsTitles.vue';
import LineChart from 'src/components/LineChart.vue';
import Barchart from 'src/components/Barchart.vue';

export default {
  components: {
    CommonCard,
    Input,
    Products,
    BasicsTitles,
    LineChart,
    Barchart,
    // LineChart,
  },
  name: 'PageIndex',
  data() {
    return {
      chartData: {
        Books: 24,
        Magazine: 30,
        Newspapers: 10,
      },
      model: null,
      // options: [
      //   'Google', 'Facebook', 'Twitter', 'Apple', 'Oracle',
      // ],
      cash: 300,
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
    width: 140px;
    margin-left: 15px;
    justify-content: end;
    flex-direction: row-reverse;
  }

  &--main {
    width: 500px;
    height: 300px;

    @media screen and (max-width: 600px) {
      width: 325px;
    }

    &--secundary {
      margin-top: 15px !important;
      width: 500px;
      height: 210px;

      @media screen and (max-width: 600px) {
        width: 325px;
      }
    }
  }

  &--services {
    margin-top: 15px;
    width: 325px;
    height: 190px;

    &--box {
      // display: flex;
      margin-top: 10px;
      padding: 10px;
      align-items: center;
      height: 60px;
      border: 1px solid rgb(228, 222, 222);
      box-shadow: none;
      border-radius: 4px 4px 0px 0px;

      & > b,
      & > span {
        font-size: 11px;
      }
    }
  }
}
.icon-search {
  display: flex;
  flex-direction: end;
}
.card {
  display: flex;
  text-align: center;

  @media screen and (max-width: 800px) {
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

// Adjustemnts
.linechart{
  @media screen and (max-width: 600px) {
    width:300px !important;
  }
}
.first-input {
  margin-bottom: 20px;
  width: 200px;

  @media screen and (max-width: 600px) {
    margin-top: 20px !important;
  }
}
</style>
