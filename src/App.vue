<template>
  <div id="app">
    <router-view></router-view>
  </div>
</template>

<script>
import Vue from "vue";

import Buefy from "buefy";
import "buefy/lib/buefy.css";
import { library } from "@fortawesome/fontawesome-svg-core";
import { fas } from "@fortawesome/free-solid-svg-icons";
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";

library.add(fas);

Vue.component("font-awesome-icon", FontAwesomeIcon);

Vue.config.productionTip = false;

Vue.use(Buefy, {
  defaultIconPack: "fa"
});

export default {
  name: "app"
};
</script>

<style lang =scss>
// Import Bulma's core
@import "./sass/spacing.scss";
@import "~bulma/sass/utilities/_all";

@font-face {
  font-family: Gotham Book;
  src: url("./assets/fonts/Gotham-Book.otf") format("opentype");
}

.breadcrumb {
  &--alignHeader {
    margin-left: 8.33333%;
    margin-bottom: 0% !important;
  }
  &__sideItems {
    font-size: 14px;
  }

  & a {
    color: #aeb6c1 !important;
  }
}
// colors
$primary: #de8f75;
$primary-invert: findColorInvert($primary);
$twitter: #aeb6c1;
$twitter-invert: findColorInvert($twitter);

// Setup $colors to use as bulma classes (e.g. 'is-twitter')
$colors: (
  "white": ($white, $black),
  "black": ($black, $white),
  "light": ($light, $light-invert),
  "dark": ($dark, $dark-invert),
  "primary": ($primary, $primary-invert),
  "info": ($info, $info-invert),
  "success": ($success, $success-invert),
  "warning": ($warning, $warning-invert),
  "danger": ($danger, $danger-invert),
  "twitter": ($twitter, $twitter-invert)
);

// Links
$family-primary: "Gotham Book";
$link: $primary;
$link-invert: $primary-invert;
$link-focus-border: $primary;

// Import Bulma and Buefy styles
@import "~bulma";
@import "~buefy/src/scss/buefy";
</style>
