<template>
  <v-container grid-list-md text-xs-center id="chunk1">
    <v-layout>
      <div>
        <v-flex lg4 id="greeter"></v-flex>
      </div>
    </v-layout>
  </v-container>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component({
  components: {}
})
export default class Home extends Vue {}
</script>

<style lang="css" scoped>
#chunk1 {
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

  height: 700px;
  width: 100%;
}
#greeter {
  text-align: left;
  margin-left: 20px;
}
#header {
  font-size: 55px;
}
</style>