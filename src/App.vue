<template>
  <div id="app">
    <div class="content">
      <h1>incel gejming klubb</h1>
      <p v-if="!info" class="info">incel.gay &mdash; Laddar...</p>
      <div v-else>
        <p class="info" v-if="info.online">
          <span class="dot online"></span> incel.gay &mdash;
          {{ info.players.online }}/{{ info.players.max }} spelare online ({{
            info.version
          }})
        </p>
        <p class="info" v-else>
          <span class="dot offline"></span> incel.gay &mdash; Offline
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "App",
  data() {
    return {
      info: null,
    };
  },
  mounted() {
    axios
      .get("https://api.mcsrvstat.us/2/incel.gay")
      .then((response) => (this.info = response.data));
  },
};
</script>

<style>
:root {
  font-family: "Rubik", sans-serif;
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

.content {
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

h1 {
  font-size: 4em;
  margin: 0 0 10px 0;
  font-weight: 700;
}

.info {
  margin: 0;
  font-size: 1.5em;
  font-weight: 300;
}

.dot {
  height: 15px;
  width: 15px;
  border-radius: 50%;
  display: inline-block;
  margin-right: 5px;
}

.dot.online {
  background-color: #5cff7a;
}

.dot.offline {
  background-color: #ff5757;
}
</style>
