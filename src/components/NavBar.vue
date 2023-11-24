<script setup>
import Logo from "./Logo.vue";
import Navlinks from "./NavLinks.vue";
</script>

<template>
  <div class="container-nav">
    <Logo />
    <Navlinks />
  </div>
</template>

<style scoped>
.container-nav {
  width: 100%;
  padding: 20px 0;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
