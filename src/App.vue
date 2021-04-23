<template>
  <div class="container card-product">
    <div class="row">
      <div class="col-12 col-md-6">
        <Slider />
      </div>
      <div class="col-12 col-md-6">
        <CardContent
          :counter="counter"
          @addCount="addCount"
          @decCount="decCount"
        />
      </div>
    </div>
  </div>
</template>

<script>
import CardContent from "./components/CardContent";
import Slider from "./components/Slider";

export default {
  name: "App",
  components: {
    CardContent,
    Slider,
  },
  data: () => ({
    counter: 0,
  }),
  methods: {
    addCount() {
      return this.counter++;
    },
    decCount() {
      return this.counter--;
    },
  },
};
</script>

<style>
body {
  font-family: "Rubik", sans-serif !important;
  font-weight: normal;
  font-size: 13px !important;
  line-height: 15px !important;
  color: #2f323d;
}
.card-product {
  padding: 3.5rem 0.5rem;
}
.border-bottom {
  border-bottom: 1px solid #e1dfdf;
}
.btn {
  display: inline-block;
  font-weight: 400;
  line-height: 1.5;
  color: #212529;
  text-align: center;
  text-decoration: none;
  vertical-align: middle;
  cursor: pointer;
  -webkit-user-select: none;
  -moz-user-select: none;
  user-select: none;
  background-color: #0000;
  border: 1px solid #0000;
  padding: 0.375rem 0.75rem;
  font-size: 1rem;
  border-radius: 0.25rem;
  transition: color 0.5s ease-in-out, background-color 0.15s ease-in-out,
    border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
}
.btn:active{
  transform: scale(1.04);
}
.btn__input {
  max-width: 60px;
  background: #f6f6f6;
  border: 1px solid #e0e0e0;
  box-sizing: border-box;
  border-radius: 4px;
  margin: 0 8px;
}
.btn__outline {
  border: 1px solid #e0e0e0;
  box-sizing: border-box;
}
.btn__green {
  background: #309975;
  border-radius: 4px;
  color: #fff;
}
.yellow-card {
  background: #efeeb4;
  border-radius: 4px;
  padding: 8px;
  min-width: 163px;
}
.yellow-card img {
  margin-left: 8px;
}

@media only screen and (max-width: 500px) {
  .card-product {
    padding-top: 1rem;
  }
}
</style>
