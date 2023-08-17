<script>
import "bootstrap/dist/css/bootstrap.css";
import "bootstrap";

import AppNav from "./components/AppNav.vue";
export default {
  components: {
    AppNav,
  },
};
</script>

<template>
  <AppNav />
  <router-view></router-view>
</template>

<style></style>
