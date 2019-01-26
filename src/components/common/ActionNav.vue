<template>
  <v-container grid-list-md text-xs-center id="chunk1">
    <v-layout id="bt-menu" class="bt-menu">
      <v-toolbar fixed app dense flat>
        <div @click="init">
          <a href="#" class="bt-menu-trigger">
            <span>Menu</span>
          </a>
        </div>

        <v-spacer></v-spacer>
        <v-toolbar-title>Owen Caulfield</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-toolbar-items class="hidden-sm-and-down">
          <v-btn flat to="/register">Sign Up</v-btn>

          <v-btn flat to="/dashboard/home">Dashboard</v-btn>
          <v-btn flat>Log Out</v-btn>
        </v-toolbar-items>
        <v-btn dark color="#7232f9" to="/login">Login</v-btn>
      </v-toolbar>
      <ul>
        <li>
          <a href="#" class="bt-icon icon-browser">
            <v-icon large dark>home</v-icon>
          </a>
        </li>
        <li>
          <a href="#" class="bt-icon icon-email">
            <v-icon large dark>email</v-icon>
          </a>
        </li>
        <li>
          <a href="#" class="bt-icon icon-bubble">
            <v-icon large dark>chat</v-icon>
          </a>
        </li>
        <li>
          <a href="#" class="bt-icon icon-calculator">
            <v-icon large dark>code</v-icon>
          </a>
        </li>
        <li>
          <a href="#" class="bt-icon icon-cd">
            <v-icon large dark>dialpad</v-icon>
          </a>
        </li>
      </ul>
      <ul>
        <li>
          <a href="#" class="bt-icon icon-newspaper">
            <v-icon large dark>money</v-icon>
          </a>
        </li>
        <li>
          <a href="#" class="bt-icon icon-file-add">
            <v-icon large dark>flag</v-icon>
          </a>
        </li>
        <li>
          <a href="#" class="bt-icon icon-trash">
            <v-icon large dark>hotel</v-icon>
          </a>
        </li>
      </ul>
    </v-layout>
  </v-container>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import { EventBus } from "@/event-bus";
import actionTrigger from "@/helpers/scripts/actionNav";

@Component({
  components: {}
})
export default class ActionNav extends Vue {
  init() {
    var menu = document.getElementById("bt-menu"),
      trigger = menu.querySelector("a.bt-menu-trigger"),
      resetMenu = function() {
        menu.classList.remove("bt-menu-open");
        menu.classList.add("bt-menu-close");
      },
      closeClickFn = function(ev) {
        resetMenu();
        overlay.removeEventListener("click", closeClickFn);
      };

    var overlay = document.createElement("div");
    overlay.className = "bt-overlay";
    menu.appendChild(overlay);

    if (menu.classList.contains("bt-menu-open")) {
      resetMenu();
    } else {
      menu.classList.remove("bt-menu-close");
      menu.classList.add("bt-menu-open");
      overlay.addEventListener("click", closeClickFn);
    }
  }

  created() {
    EventBus.$on("toggle-menu", () => {
      this.init();
    });
  }
}
</script>

<style lang="css" scoped>
*,
*:after,
*::before {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}

body {
  background: #faae33;
}

.container {
  padding: 80px;
}

.bt-menu {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 0;
  border-width: 0px;
  border-style: solid;
  border-color: rgb(88, 88, 88);
  background-color: rgba(0, 0, 0, 0);
  -webkit-backface-visibility: hidden;
  -webkit-transition: border-width 0.3s, background-color 0.3s, height 0s 0.3s;
  transition: border-width 0.3s, background-color 0.3s, height 0s 0.3s;
}

.bt-menu.bt-menu-open {
  height: 100%;
  border-width: 0px 90px 90px 0px;
  background-color: rgba(100, 100, 100, 0.3);
  -webkit-transition: border-width 0.3s, background-color 0.3s;
  transition: border-width 0.3s, background-color 0.3s;
}

.bt-overlay {
  position: absolute;
  width: 100%;
}

.bt-menu-open .bt-overlay {
  height: 100%;
}

.bt-menu-trigger {
  position: fixed;
  z-index: 100;
  display: block;
  width: 50px;
  height: 50px;
  cursor: pointer;
}

.bt-menu-trigger span {
  position: absolute;
  right: 0;
  color: #6e45f3;
  display: block;
  width: 100%;
  height: 4px;
  background-color: #6e45f3;
  font-size: 0px;
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  -webkit-transition: background-color 0.3s;
  transition: background-color 0.3s;
}

.bt-menu-open .bt-menu-trigger span {
  background-color: transparent;
}

.bt-menu-trigger span:before,
.bt-menu-trigger span:after {
  position: absolute;
  left: 0;
  width: 100%;
  height: 100%;
  background: #6e45f3;
  content: "";
  -webkit-transition: -webkit-transform 0.3s;
  transition: transform 0.3s;
}

.bt-menu-trigger span:before {
  -webkit-transform: translateY(-250%);
  transform: translateY(-250%);
}

.bt-menu-trigger span:after {
  -webkit-transform: translateY(250%);
  transform: translateY(250%);
}

.bt-menu-open .bt-menu-trigger span:before {
  -webkit-transform: translateY(0) rotate(45deg);
  transform: translateY(0) rotate(45deg);
}

.bt-menu-open .bt-menu-trigger span:after {
  -webkit-transform: translateY(0) rotate(-45deg);
  transform: translateY(0) rotate(-45deg);
}

.bt-menu ul {
  position: fixed;
  margin: 0;
  padding: 0;
  list-style: none;
}

.bt-menu ul:first-of-type {
  right: 0;
  bottom: 75px;
}

.bt-menu ul:nth-of-type(2) {
  right: 75px;
  bottom: 0px;
}

.bt-menu ul:first-of-type li,
.bt-menu ul li a {
  display: block;
}

.bt-menu ul:nth-of-type(2) li {
  display: inline-block;
  font-size: 0px;
}

.bt-menu ul li {
  visibility: hidden;
  width: 90px;
  height: 90px;
  line-height: 90px;
  opacity: 0;
  -webkit-transition: -webkit-transform 0.3s, opacity 0.2s, visibility 0s 0.3s;
  transition: transform 0.3s, opacity 0.2s, visibility 0s 0.3s;
}

/* First menu */
.bt-menu ul:first-of-type li:first-child {
  -webkit-transform: translate3d(0, 500%, 0);
  transform: translate3d(0, 500%, 0);
}

.bt-menu ul:first-of-type li:nth-child(2) {
  -webkit-transform: translate3d(0, 400%, 0);
  transform: translate3d(0, 400%, 0);
}

.bt-menu ul:first-of-type li:nth-child(3) {
  -webkit-transform: translate3d(0, 300%, 0);
  transform: translate3d(0, 300%, 0);
}

.bt-menu ul:first-of-type li:nth-child(4) {
  -webkit-transform: translate3d(0, 200%, 0);
  transform: translate3d(0, 200%, 0);
}

.bt-menu ul:first-of-type li:nth-child(5) {
  -webkit-transform: translate3d(0, 100%, 0);
  transform: translate3d(0, 100%, 0);
}

/* Second menu */
.bt-menu ul:nth-of-type(2) li:first-child {
  -webkit-transform: translate3d(300%, 0, 0);
  transform: translate3d(300%, 0, 0);
}

.bt-menu ul:nth-of-type(2) li:nth-child(2) {
  -webkit-transform: translate3d(200%, 0, 0);
  transform: translate3d(200%, 0, 0);
}

.bt-menu ul:nth-of-type(2) li:nth-child(3) {
  -webkit-transform: translate3d(100%, 0, 0);
  transform: translate3d(100%, 0, 0);
}

.bt-menu.bt-menu-open ul:first-of-type li,
.bt-menu.bt-menu-open ul:nth-of-type(2) li {
  visibility: visible;
  opacity: 1;
  -webkit-transition: -webkit-transform 0.3s, opacity 0.3s 0.1s;
  transition: transform 0.3s, opacity 0.3s;
  -webkit-transform: translate3d(0, 0, 0);
  transform: translate3d(0, 0, 0);
}

.bt-menu ul li a {
  display: block;
  outline: none;
  color: transparent;
  text-align: center;
  text-decoration: none;
  font-size: 0px;
}

.bt-menu ul li a:before {
  color: #fff;
  font-size: 48px;
  opacity: 0.5;
  -webkit-transition: opacity 0.2s;
  transition: opacity 0.2s;
}

.bt-menu ul li a:hover:before,
.bt-menu ul li a:focus:before {
  opacity: 1;
}

@media screen and (max-height: 31.125em) {
  .bt-menu ul li a:before {
    font-size: 32px;
  }

  .bt-menu ul:first-of-type li {
    height: 60px;
    line-height: 60px;
  }

  .bt-menu ul:nth-of-type(2) li {
    width: 60px;
  }
}
</style>