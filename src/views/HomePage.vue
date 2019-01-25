<template>
  <v-container grid-list-xl id="homeLayout">
    <v-layout row wrap>
      <div class="blockZero"></div>
    </v-layout>
    <v-layout row wrap>
      <div class="slideSection">
        <div class="demo plain">
          <section>
            <header></header>
            <div class="separator"></div>
            <footer></footer>
          </section>
        </div>
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
  height: 400px;
}

.separator {
  width: var(--width);
  height: var(--height);
  background-image: linear-gradient(
    to bottom right,
    var(--top-color),
    var(--top-color) 50%,
    var(--bottom-color) 50%,
    var(--bottom-color)
  );
}

.separator.reverse {
  background-image: linear-gradient(
    to bottom left,
    var(--top-color),
    var(--top-color) 50%,
    var(--bottom-color) 50%,
    var(--bottom-color)
  );
}

.separator.vertical.reverse {
  background-image: linear-gradient(
    to top right,
    var(--top-color),
    var(--top-color) 50%,
    var(--bottom-color) 50%,
    var(--bottom-color)
  );
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
