<template>
  <v-app id="app">
    <v-content id="bg">
      <action-nav/>
      <router-view class="view"/>
    </v-content>
  </v-app>
</template>
  
<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Nav from "@/components/common/Nav.vue"; // @ is an alias to /src
import ActionNav from "@/components/common/ActionNav.vue";

@Component({
  components: {
    Nav,
    ActionNav
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

