<template>
  <div class="card-content my-4 my-md-0">
    <div class="card-content__header border-bottom">
      <h1 class="card-content__title">
        100% органический 10 лет корень корейского женьшеня красный Panax
        улучшить иммунную
      </h1>
      <div class="oders">
        <div class="oders__icons icon-text">
          <div class="icon-text__img">
            <img src="/img/frame 1.svg" />
            <img src="/img/frame 1.svg" />
            <img src="/img/frame 1.svg" />
            <img src="/img/frame 4.svg" />
            <img src="/img/frame 5.svg" />
          </div>
          <span class="icon-text__text">243</span>
        </div>
        <div class="oders__amount">Количество заказов: 1</div>
      </div>
    </div>
    <div class="card-content__payment border-bottom">
      <div class="payment">
        <h3 class="payment__price">15 000 000 сум</h3>
        <div>
          <span class="payment__old-price">20 000 000 сум</span>
          <span class="payment__discount">-25%</span>
        </div>
      </div>
      <div class="payment__cards">
        <span class="">Методы оплаты:</span>
        <div>
          <img src="/img/payme.png" alt="Payme" />
          <img src="/img/humo.png" alt="Humo" />
          <img src="/img/Click.png" alt="Click" />
        </div>
      </div>
      <div class="payment__cards">
        <span>Методы доставки:</span>
        <div>
          <img src="/img/delivery.svg" alt="delivery" />
          <span>Доставка продавца</span>
        </div>
        <div>
          <img src="/img/product.svg" alt="product" />
          <span>Самовывоз</span>
        </div>
      </div>
    </div>
    <div class="card-content__amount product-quantity">
      <div class="product-quantity__total">
        <p>Количество</p>
        <div class="product-quantity__picker">
          <div class="picker">
            <button @click="onDecCount" class="btn btn__outline" type="button">
              <img src="/img/icon-min.svg" alt="Payme" />
            </button>
            <input
              class="btn btn__input"
              type="text"
              :value="value"
              @input="input"
            />
            <button
              @click="onAddCount"
              class="btn btn__outline"
              type="button"
            >
              <img src="/img/icon-plus.svg" alt="Payme" />
            </button>
          </div>
          <div class="icon-text yellow-card">
            <div class="icon-text__img">
              <img src="/img/complete.svg" />
            </div>
            <span class="icon-text__text">в наличии 1 245 шт.</span>
          </div>
        </div>
      </div>
      <div class="product-quantity__buttons border-bottom">
        <div class="btn__group">
          <button class="btn btn__green">Купить в один клик</button>
          <button class="btn btn__outline">Связаться с продавцом</button>
        </div>
      </div>
      <div class="card-content__footer">
        <p>* Стоимость доставки заказов до 40 000 сум - договорная</p>
        <p>** Бесплатная доставка при заказе от 40 000 сум</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardContent",
  props: {
    value: Number,
  },
  data: () => ({}),
  methods: {
    input(e) {
      this.$emit("input", +e.target.value);
    },
    onAddCount() {
      this.$emit("addCount", this.value);
    },
    onDecCount() {
      if (this.value) {
        this.$emit("decCount", this.value);
      }
    },
  },
};
</script>

<style scoped>
.product-quantity__picker {
  display: flex;
  align-items: center;
  flex-wrap: wrap;
}
.card-content__header {
  padding-bottom: 1rem;
}
.card-content__title {
  font-size: 20px;
  line-height: 24px;
  color: #2f323d;
}
.card-content__amount {
  padding: 1.1rem 0;
}
.icon-text {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: space-between;
  max-width: 140px;
}
.icon-text__text {
  font-size: 11px;
  line-height: 140%;
}
.icon-text__img {
  margin-right: 6px;
}

.oders {
  display: flex;
  align-items: center;
}
.oders__icons img {
  padding: 0 0.2rem;
}
.oders__amount {
  font-size: 11px;
  line-height: 140%;
  margin-left: 3.7rem;
}

.card-content__payment {
  padding-top: 1.9rem;
}

.payment__price {
  font-weight: 500;
  font-size: 1.8rem;
  line-height: 125%;
}
.payment__old-price {
  line-height: 15px;
  color: #596178;
  text-decoration: line-through;
  margin-right: 1.8rem;
}
.payment__discount {
  display: inline-block;
  background: #ff5530;
  border-radius: 6px;
  padding: 5px 2px;
  line-height: 140%;
  color: #ffffff;
}
.payment__cards {
  padding: 1rem 0;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
}
.payment__cards span {
  margin-right: 8px;
}
.payment__cards img {
  margin: 0 0.5rem;
}
.btn__group {
  padding: 1rem 0;
}
.btn__group .btn {
  margin: 0.5rem 1rem 0.5rem 0;
  padding-left: 2rem;
  padding-right: 2rem;
}
.card-content__footer {
  padding-top: 16px;
  font-size: 15px;
  line-height: 140%;
}
.picker {
  min-width: 180px;
  padding: 1rem 0;
}

@media only screen and (max-width: 500px) {
  .btn__group .btn {
    margin-top: 1rem;
  }
  .payment__cards {
    flex-direction: column;
    align-items: flex-start;
  }
  .payment__cards span {
    margin-right: 8px;
  }
  .payment__cards img {
    margin: 1rem 0.8rem 1rem 0;
  }
}
</style>