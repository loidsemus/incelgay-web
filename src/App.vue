<template>
  <div id="app">
    <Hero />
  </div>
</template>

<script>
import Hero from "./components/Hero";

export default {
  name: "App",
  components: {
    Hero
  }
};
</script>

<style>
:root {
  font-family: "Rubik", sans-serif;
  background-color: #202225;
  color: #f2ffff;
}

body,
html {
  height: 100%;
  margin: 0;
  padding: 0;
}

#app {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 0 128px;
}

@media screen and (max-width: 900px) {
  #app {
    padding: 0 32px;
  }
}
</style>
