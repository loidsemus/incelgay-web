<template>
  <div
    class="banner px-2 flex absolute blurple bottom-0 right-0 w-full
     py-4 md:px-8 xl:px-72 2xl:px-96 xl:justify-around text-xl justify-between items-center"
  >
    <p class="inline">incel gejming klubb: kuk-o-boll-unionen på Discord</p>
    <a
      class="bg-white text-blurple py-2 px-4 rounded-lg transform duration-300 hover:-translate-y-0.5 hover:shadow-lg hover:scale-105"
      href="https://discord.gg/p9JC825jqQ"
    >
      gå med
    </a>
    <svg
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 1440 320"
      class="wave absolute bottom-3/4 md:bottom-1/2 left-0"
    >
      <path
        fill="#7289DA "
        fill-opacity="1"
        d="M0,64L30,85.3C60,107,120,149,180,176C240,203,300,213,360,218.7C420,224,480,224,540,213.3C600,203,660,181,720,186.7C780,192,840,224,900,208C960,192,1020,128,1080,106.7C1140,85,1200,107,1260,106.7C1320,107,1380,85,1410,74.7L1440,64L1440,320L1410,320C1380,320,1320,320,1260,320C1200,320,1140,320,1080,320C1020,320,960,320,900,320C840,320,780,320,720,320C660,320,600,320,540,320C480,320,420,320,360,320C300,320,240,320,180,320C120,320,60,320,30,320L0,320Z"
      ></path>
    </svg>
    <img
      src="@/assets/images/roblox.png"
      class="hidden 2xl:block absolute right-24 bottom-48 w-64"
    />
  </div>
</template>

<script>
export default {
  name: "BottomBanner"
};
</script>

<style scoped>
.wave {
  z-index: -1;
}

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
