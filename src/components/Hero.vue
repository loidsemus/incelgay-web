<template>
  <div class="hero">
    <h1>incel gejming klubb</h1>
    <p v-if="errored" class="info error">
      <span class="dot error"></span> Kunde inte ladda serverstatus
    </p>
    <div v-else>
      <transition name="fade" mode="out-in">
        <p class="info" v-if="loading" key="loading">
          <span class="dot loading"></span> mc.incel.gay &mdash; Laddar...
        </p>
        <p class="info" v-else key="loaded">
          <span
            class="dot"
            v-bind:class="{
              online: info.online,
              offline: !info.online
            }"
          ></span>
          mc.incel.gay &mdash;
          <span v-if="info.online">
            {{ info.players.online }}/{{ info.players.max }} spelar just nu
            <span style="color: #808080">({{ info.version }})</span>
          </span>
          <span v-else>Offline</span>
        </p>
      </transition>
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
      errored: false
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
  }
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

.dot.offline,
.dot.error {
  background-color: #ff5757;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.25s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active in <2.1.8 */ {
  opacity: 0;
}

@media screen and (max-width: 900px) {
  h1 {
    font-size: 3em;
  }

  .info {
    font-size: 1.25em;
  }

  .dot {
    width: 10px;
    height: 10px;
  }
}
</style>
