<template>
  <section class="section">
    <div class="container has-text-centered">
      <div class="column is-4 is-offset-4">
        <h3 class="title has-text-grey">Register</h3>
        <p class="subtitle has-text-grey">Please enter your information</p>
        <div class="box">
          <!-- @submit handles any form of submission. -->
          <!-- .prevent keeps the event from bubbling around and doing anything else. -->
          <form @submit.prevent="handleSubmit">
            <div class="field">
              <div class="control">
                <input
                  class="input is-large"
                  type="text"
                  placeholder="First name"
                  v-model="user.firstName"
                  autofocus
                >
              </div>
            </div>

            <div class="field">
              <div class="control">
                <input
                  class="input is-large"
                  type="text"
                  placeholder="Last name"
                  v-model="user.lastName"
                >
              </div>
            </div>

            <div class="field">
              <div class="control">
                <input class="input is-large" type="email" placeholder="Email" v-model="user.email">
              </div>
            </div>

            <div class="field">
              <div class="control">
                <input class="input is-large" placeholder="Username" v-model="user.userName">
              </div>
            </div>

            <div class="field">
              <div class="control">
                <input
                  class="input is-large"
                  type="text"
                  placeholder="Password"
                  v-model="user.password"
                >
              </div>
            </div>
            <button class="button is-block is-info is-large is-fullwidth" type="submit">Submit</button>
            <div class="errors-container" v-if="errors">{{errors}}</div>
          </form>
        </div>
        <p class="has-text-grey">
          <router-link to="/login">Login</router-link>
        </p>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component({
  components: {}
})
export default class RegistrationForm extends Vue {
  private isBusy: boolean = false;
  private errors: string = "";
}
</script>

<style lang="scss" scoped>
</style>
 