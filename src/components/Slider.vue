<template>
  <div class="container-slide">
    <hooper group="group1" class="top-slide">
      <slide v-for="(slide, indx) in slides" :key="indx" :index="indx">
        <div class="top-slide__inner">
          <img class="hooper__img" :src="slide" />
        </div>
      </slide>
    </hooper>

    <hooper
      class="bottom-slide"
      group="group1"
      :itemsToShow="7"
      vertical
      autoPlay
      :playSpeed="10000"
      :settings="hooperSettings"
      centerMode
    >
      <slide v-for="(slide, indx) in slides" :key="indx" :index="indx">
        <div class="bottom-slide__inner">
          <img class="hooper__img" :src="slide" />
        </div>
      </slide>
      <hooper-navigation slot="hooper-addons"></hooper-navigation>
    </hooper>
  </div>
</template>

<script>
import { Hooper, Slide, Navigation as HooperNavigation } from "hooper";
import "hooper/dist/hooper.css";
export default {
  name: "Slider",
  data: () => ({
    slides: [
      "https://images.unsplash.com/photo-1543163521-1bf539c55dd2?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1600&q=80",
      "https://images.unsplash.com/photo-1549049950-48d5887197a0?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=700&q=80",
      "/img/02.png",
      "https://images.unsplash.com/photo-1580870069867-74c57ee1bb07?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=675&q=80",
      "https://images.unsplash.com/photo-1543163521-1bf539c55dd2?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1600&q=80",
      "https://images.unsplash.com/photo-1549049950-48d5887197a0?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=700&q=80",
      "/img/02.png",
      "https://images.unsplash.com/photo-1580870069867-74c57ee1bb07?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=675&q=80",
      "https://images.unsplash.com/photo-1543163521-1bf539c55dd2?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1600&q=80",
      "https://images.unsplash.com/photo-1549049950-48d5887197a0?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=700&q=80",
      "/img/02.png",
      "https://images.unsplash.com/photo-1580870069867-74c57ee1bb07?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=675&q=80",
    ],
    hooperSettings: {
      itemsToShow: 3,
      breakpoints: {
        500: {
          itemsToShow: 6,
        },
        800: {
          itemsToShow: 8,
        },
      },
    },
  }),
  components: {
    Hooper,
    Slide,
    HooperNavigation,
  },
};
</script>

<style >
.hooper__img {
  width: 100%;
  height: 100%;
  object-fit: contain;
}
.top-slide {
  height: 100%;
  max-width: 85%;
  margin-left: 80px;
  border: 1px solid #e0e0e0;
  box-sizing: border-box;
  border-radius: 8px;
  overflow: hidden;
}
.top-slide__inner {
  background: #ffffff;
  height: 100%;
  padding: 70px;
}

.bottom-slide {
  position: absolute;
  top: 0;
  height: 100%;
  width: 10%;
}
.bottom-slide__inner {
  background: #ffffff;
  padding: 5px;
  border: 1px solid #e0e0e0;
  box-sizing: border-box;
  border-radius: 4px;
  width: 65px;
  height: 65px;
  margin: 0 auto;
}
.container-slide {
  position: relative;
  padding: 0 1rem;
  height: 100%;
}
.hooper-list {
  min-width: 68px;
  position: relative;
}
.hooper-navigation {
  width: 36px !important;
  height: 36px !important;
}
.hooper-navigation.is-vertical .hooper-prev,
.hooper-navigation.is-vertical .hooper-next {
  background: #ffffff;
  border: 1px solid #e0e0e0;
  box-sizing: border-box;
  border-radius: 4px;
  padding: 12px 14px;
  left: 50% !important;
  transform: translateX(-50%);
}
.hooper-next:focus {
  outline: none;
}
.hooper-prev:focus {
  outline: none;
}
.hooper:focus {
  outline: none;
}
.is-current .bottom-slide__inner {
  border: 1px solid #4ca780;
}
@media only screen and (max-width: 500px) {
  .hooper-navigation.is-vertical .hooper-prev,
  .hooper-navigation.is-vertical .hooper-next {
    padding: 0;
  }
  .top-slide__inner {
    padding: 1rem;
  }
}
</style>
