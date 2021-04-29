<template lang="">
  <div>
    <div class="my-card--products--cards">
      <div class="flex my-card--products--container">
        <img class="my-card--products--cards--image" :src="imageSrc"/>
        <div class="my-card--products--cards--itens">
          <b>{{ product }}</b>
          <span>Quantidade: {{ amount }}</span>
        </div>
        <div class="my-card--products--cards--itens">
          <span>Preço / Promoção</span>
          <b>R${{ normalPrice }} / <b>R${{ promotionPrice }}</b></b>
        </div>
      </div>
    </div>
    <div v-if="havePoint" class="flex my-card--products--score">
      <span>Pontos: <b>{{ points }}</b> pts</span>
      <span>Resgates: <b>{{ redeemPoints }}</b> pts</span>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    product: {
      type: String,
      default: '',
    },
    amount: {
      type: String,
      default: '',
    },
    normalPrice: {
      type: String,
      default: '',
    },
    promotionPrice: {
      type: String,
      default: '',
    },
    imageSrc: {
      type: String,
      default: '',
    },
    points: {
      type: Number,
      default: 0,
    },
    redeemPoints: {
      type: Number,
      default: 0,
    },
    havePoint: {
      type: Boolean,
      default: true,
    },
  },
};
</script>
<style lang="scss">
.my-card {

  &--products {
    // margin-top: 15px;
    width: 325px;
    height: 400px;

    &--title {
      justify-content: space-between;
    }

    &--container {
      justify-content: space-between;
    }

    &--cards {
      margin-top: 10px;
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
          font-weight: normal;

          & > b {
            color:green;
            font-weight: normal;
          }
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

      & > span {
        & > b {
          color:orange;
          font-weight: normal;
        }
        // text-transform: none;
      }
    }
  }
}
</style>
