<template>
  <v-container grid-list-xl id="homeLayout">
    <v-layout row wrap>
      <home id="home"/>
    </v-layout>
    <v-layout row wrap>
      <div>
        <v-flex lg4 id="chunkTwo">
          <h1 id="header">Hi, I'm</h1>
          <h1 id="header">Owen 👉</h1>
        </v-flex>
      </div>
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
#home {
  background: linear-gradient(
    to right,
    hsl(0, 0%, 96%) 0%,
    hsl(191.61, 9.32%, 96.74%) 13.6%,
    hsl(191.58, 21.18%, 96.12%) 25.2%,
    hsl(191.54, 29.27%, 96.19%) 34.8%,
    hsl(191.49, 34.27%, 96%) 42.8%,
    hsl(191.42, 37.47%, 96.59%) 49.5%,
    hsl(191.35, 39.66%, 96.01%) 55.1%,
    hsl(191.26, 41.27%, 95.31%) 59.8%,
    hsl(191.17, 42.51%, 93.55%) 64.1%,
    hsl(191.07, 43.51%, 91.77%) 68%,
    hsl(190.98, 44.35%, 89.05%) 71.9%,
    hsl(190.88, 45.04%, 87.45%) 76%,
    hsl(190.8, 45.6%, 85.06%) 80.6%,
    hsl(190.73, 46.03%, 83.96%) 85.9%,
    hsl(190.68, 46.3%, 81.24%) 92.3%,
    hsl(190.67, 46.39%, 79.98%) 100%
  );

  height: 700px;
  max-width: 100% !important;
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
</style>
