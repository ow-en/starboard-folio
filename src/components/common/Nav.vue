<template>
  <div>
    <v-toolbar fixed app dense flat>
      <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
      <v-toolbar-title>Some Application Title</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn flat to="/register">Sign Up</v-btn>

        <v-btn flat to="/dashboard/home">Dashboard</v-btn>
        <v-btn flat>Log Out</v-btn>
      </v-toolbar-items>
      <v-btn color="primary" to="/login">Login</v-btn>
    </v-toolbar>
    <v-content>
      <v-container fluid fill-height>
        <v-layout justify-center align-center>
          <v-flex text-xs-center></v-flex>
        </v-layout>
      </v-container>
    </v-content>
    <v-footer app></v-footer>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";
import { EventBus } from "../.././event-bus";
import { mapGetters } from "vuex";

@Component({
  computed: mapGetters({})
})
export default class Nav extends Vue {
  drawer: boolean = false;
}
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.router-link-exact-active {
  color: #209cee !important;
}
</style>

