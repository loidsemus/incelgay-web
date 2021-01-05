<template>
  <div class="hero">
    <h1>incel gejming klubb</h1>
    <p v-if="errored" class="info error">Kunde inte ladda serverstatus</p>
    <div v-else>
      <p v-if="loading" class="info">
        <span class="dot loading"></span> mc.incel.gay &mdash; Laddar...
      </p>
      <div v-else>
        <p class="info" v-if="info.online">
          <span class="dot online"></span> mc.incel.gay &mdash;
          {{ info.players.online }}/{{ info.players.max }} spelar just nu
          <span style="color: #808080">(MC {{ info.version }})</span>
        </p>
        <p class="info" v-else>
          <span class="dot offline"></span> mc.incel.gay &mdash; Offline
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "Hero",
  data() {
    return {
      loading: true,
      info: null,
      errored: false,
    };
  },
  mounted() {
    axios
      .get("https://api.mcsrvstat.us/2/mc.incel.gay")
      .then((response) => (this.info = response.data))
      .catch((error) => {
        console.log(error);
        this.errored = true;
      })
      .finally(() => (this.loading = false));
  },
};
</script>

<style>
.hero {
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  justify-content: center;
  height: 100%;
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

.info.error {
  color: #ff5757;
}

.dot.loading {
  background-color: #477bff;
}

.dot.online {
  background-color: #5cff7a;
}

.dot.offline {
  background-color: #ff5757;
}
</style>