<template>
  <!-- <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/login">Login</router-link> |
    <router-link to="/categories">Category</router-link>
  </nav> -->
  <component :is="layout">
    <router-view />
  </component>
</template>

<script>
import EmptyLayout from "@/layouts/EmptyLayout";
import MainLayout from "@/layouts/MainLayout";
export default {
  computed: {
    layout() {
      console.log("route", this.$route);
      return (this.$route.meta.layout || "empty") + "-layout";
    },
  },
  components: { EmptyLayout, MainLayout },
};
</script>

<style lang="scss">
@import "~materialize-css/dist/css/materialize.min.css";
@import "assets/index.css";
</style>
