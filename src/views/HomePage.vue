<template>
  <v-container grid-list-xl id="homeLayout">
    <v-layout row wrap>
      <div class="blockZero"></div>
    </v-layout>
    <v-layout row wrap>
      <div class="slideSection">
        <header>
          <h1>Header Content</h1>
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" preserveAspectRatio="none">
            <polygon
              class="svg--sm"
              fill="#f5f5f5"
              points="0,0 30,100 65,21 90,100 100,75 100,100 0,100"
            ></polygon>
            <polygon
              class="svg--lg"
              fill="#f5f5f5"
              points="12,10 25,100 33,-21 45,100 50,75 45,100 72,20 85,100 95,50 100,80 100,100 0,100"
            ></polygon>
          </svg>
        </header>

        <section>
          <h1>Section Content</h1>
        </section>
      </div>
      <div class="blockOne"></div>
      <div class="blockTwo"></div>
      <div class="blockThree"></div>
      <div class="blockFour"></div>
      <div class="blockFive"></div>
      <div class="blockSix"></div>
      <div class="blockSeven"></div>
    </v-layout>
  </v-container>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Home from "./Home.vue";

@Component({
  components: {
    Home
  }
})
export default class HomePage extends Vue {}
</script>

<style lang="css" scoped>
.blockZero {
  background: linear-gradient(
    to right,
    hsl(0, 0%, 96%) 0%,
    hsl(247.89, 6.49%, 95.71%) 7.3%,
    hsl(247.94, 20.93%, 94.87%) 14.2%,
    hsl(248.04, 36.14%, 93.56%) 20.8%,
    hsl(248.17, 48.84%, 91.81%) 27%,
    hsl(248.35, 58.57%, 89.66%) 33%,
    hsl(248.58, 65.86%, 87.16%) 38.9%,
    hsl(248.87, 71.33%, 84.33%) 44.8%,
    hsl(249.23, 75.5%, 81.22%) 50.7%,
    hsl(249.68, 78.72%, 77.86%) 56.7%,
    hsl(250.25, 81.27%, 74.31%) 63%,
    hsl(250.96, 83.29%, 70.66%) 69.5%,
    hsl(251.83, 84.89%, 67.02%) 76.4%,
    hsl(252.82, 86.12%, 63.66%) 83.7%,
    hsl(253.74, 86.95%, 61.05%) 91.5%,
    hsl(254.16, 87.25%, 60%) 100%
  );

  height: 260px;
  width: 100% !important;
}

.slideSection {
  width: 100%;
}

header {
  position: relative;
  height: 300px;
  background-image: linear-gradient(#33ffed, #674fec);
}

h1 {
  padding: 100px 0;
  font: 44px "Arial";
  text-align: center;
}

header h1 {
  color: white;
}

svg {
  position: absolute;
  bottom: 0;
  width: 100%;
  height: 100px;
}

@media (max-width: 699px) {
  .svg--lg {
    display: none;
  }
}

@media (min-width: 700px) {
  .svg--sm {
    display: none;
  }
}

#homeLayout {
  padding-top: 0px !important;
  max-width: 100% !important;
}

#chunkTwo {
  height: 700px;
  background: lightgray;
  max-width: 100%;
}

.blockOne {
  background-color: #013a6b;
  background-image: -webkit-linear-gradient(30deg, #33ffed 50%, #f5f5f5 50%);
  min-height: 500px;
  width: 100%;
}

.blockTwo {
  background-color: #34adff;
  background-image: -webkit-linear-gradient(150deg, #674fec 35%, #f5f5f5 35%);
  min-height: 400px;
  width: 100%;
}

.blockThree {
  background-color: #aea78e;
  min-height: 260px;
  width: 100%;
}

.blockFour {
  background-color: #e0e0e0;
  min-height: 260px;
  width: 100%;
}

.blockFive {
  background-color: #efeeef;
  min-height: 260px;
  width: 100%;
}

.blockSix {
  background-color: #34adff;
  background-image: -webkit-linear-gradient(30deg, #33ffed 45%, #aea78e 45%);
  min-height: 400px;
  width: 100%;
}

.blockSeven {
  background-color: #013a6b;
  background-image: -webkit-linear-gradient(150deg, #013a6b 35%, #004e95 35%);
  min-height: 200px;
  width: 100%;
}
</style>
