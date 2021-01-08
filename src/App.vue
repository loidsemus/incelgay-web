<template>
  <div id="app" class="h-full flex flex-col justify-center">
    <Hero />
    <BotBanner />
  </div>
</template>

<script>
import Hero from "./components/Hero";
import BotBanner from "./components/BotBanner";

export default {
  name: "App",
  components: {
    Hero,
    BotBanner
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
  margin: 0;
  padding: 0;
}

.text-blurple {
  color: #7289da;
}

.blurple {
  background-color: #7289da;
}
</style>
