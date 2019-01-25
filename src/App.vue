<template>
  <v-app id="app">
    <v-content id="bg">
      <router-view class="view"/>
      <Nav/>
    </v-content>
  </v-app>
</template>
  
<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Nav from "@/components/common/Nav.vue"; // @ is an alias to /src

@Component({
  components: {
    Nav
  }
})
export default class App extends Vue {}
</script>

<style lang="css">
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

#bg {
}
</style>

