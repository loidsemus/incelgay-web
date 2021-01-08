<template>
  <div
    class="px-2 flex absolute blurple gradient bottom-0 right-0 w-full py-4 md:px-8 xl:px-72 2xl:px-96 xl:justify-around text-xl justify-between items-center"
  >
    <p class="inline">incel gejming klubb: kuk-o-boll-unionen på Discord</p>
    <a
      class="bg-white text-blurple py-2 px-4 rounded-lg transform duration-300 hover:-translate-y-0.5 hover:shadow-lg hover:scale-105"
      href="https://discord.gg/p9JC825jqQ"
    >
      gå med
    </a>
    <img
      src="@/assets/images/discord.png"
      class="hidden 2xl:block absolute left-16 bottom-1/3 rounded-2xl w-32 
      transform duration-300 hover:-translate-y-2 hover:scale-105 hover:shadow-lg"
    />
  </div>
</template>

<script>
export default {
  name: "BottomBanner"
};
</script>

<style scoped>
.text-blurple {
  color: #7289da;
}

.blurple {
  background-color: #7289da;
}

.blurple.gradient {
  background: linear-gradient(
    90deg,
    rgba(95, 119, 203, 1) 0%,
    rgba(114, 137, 218, 1) 100%
  );
}
</style>
