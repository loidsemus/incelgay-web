<template>
  <div class="mx-auto flex flex-col justify-center h-full relative pb-48">
    <h1 class="text-7xl mb-4 font-bold">incel gejming klubb</h1>
    <transition name="fade" mode="out-in">
      <p class="info" v-if="loading" key="loading">
        <span class="dot loading"></span> mc.incel.gay &mdash; Laddar...
      </p>
      <template v-else>
        <p v-if="errored" class="info error">
          <span class="dot error"></span> Kunde inte ladda serverstatus
        </p>
        <p class="info" v-else>
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
            <span class="text-gray-500">({{ info.version }})</span>
          </span>
          <span v-else>Offline</span>
        </p>
      </template>
    </transition>
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
.info {
  @apply text-2xl font-light;
}

.dot {
  @apply animate-pulse h-4 w-4 inline-block rounded-full mr-1 relative;
}

.info.error {
  @apply text-red-400;
}

.dot.loading {
  @apply bg-blue-400;
}

.dot.online {
  @apply bg-green-400;
}

.dot.offline,
.dot.error {
  @apply bg-red-400;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.25s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active in <2.1.8 */ {
  opacity: 0;
}
</style>
