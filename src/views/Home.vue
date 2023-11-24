<script setup>
import BackgroundImage from "../components/BackgroundImage.vue";
import NavBar from "../components/NavBar.vue";
import Layout from "../components/Layout.vue";
import LeftScrollBar from "../components/LeftScrollBar.vue";
import TextContent from "../components/TextContent.vue";
import Slider from "../components/Slider.vue";
</script>

<template>
  <div>
    <BackgroundImage />
    <Layout>
      <NavBar />
      <div class="main">
        <LeftScrollBar />
        <TextContent />
        <Slider />
      </div>
    </Layout>
  </div>
</template>

<style scope>
.main {
  display: flex;
  gap: 10px;
}
</style>
