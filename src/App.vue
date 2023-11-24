<script setup>
import BackgroundImage from "./components/BackgroundImage.vue";
import NavBar from "./components/NavBar.vue";
import Layout from "./components/Layout.vue";
</script>

<template>
  <div @click="clickWhere">
    <BackgroundImage />
    <Layout>
      <NavBar />
    </Layout>
  </div>
</template>

<script></script>
