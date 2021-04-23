<template>
  <div class="container card-product">
    <div class="row">
      <div class="col-12 col-md-6">
        <Slider />
      </div>
      <div class="col-12 col-md-6">
        <CardContent />
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
};
</script>

<style>
body {
  font-family: "Rubik", sans-serif;
  font-weight: normal;
  font-size: 13px;
  line-height: 15px;
  color: #2f323d;
}
.card-product {
  padding: 3.5rem 0.5rem;
}
.border-bottom {
  border-bottom: 1px solid #e1dfdf;
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
