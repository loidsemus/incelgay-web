<template>
  <div id="app" class="h-full flex flex-col justify-center">
    <Hero />
    <BottomBanner />
  </div>
</template>

<script>
import Hero from "./components/Hero";
import BottomBanner from "./components/BottomBanner";

export default {
  name: "App",
  components: {
    Hero,
    BottomBanner
  }
};
</script>

<style>
:root {
  font-family: "Inter", sans-serif;
  background-color: #202225;
  color: #f2ffff;
}

body,
html {
  height: 100%;
}
</style>
