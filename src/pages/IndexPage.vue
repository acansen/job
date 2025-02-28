<template>
  <q-page class="column flex flex-center overflow-hidden">
    <div class="col bannar full-width overflow-hidden">
      <div class="background-loop-video">
        <video autoplay loop muted playsinline class="fullscreen-bg-video" poster="video.webp">
          <source src="mobile.webm" type="video/mp4" media="(max-width: 575px)" />
          <source src="pc.webm" type="video/mp4" />
        </video>
      </div>
      <div
        class="flex column full-height full-width justify-end"
        style="z-index: 1; position: relative; padding-top: 50px; height: 840px"
      >
        <!-- <img
          alt="Quasar logo"
          src="~assets/quasar-logo-vertical.svg"
          style="width: 200px; height: 200px"
        /> -->
      </div>
    </div>
  </q-page>
</template>
<style scoped>
.bannar {
  max-height: 840px;
  overflow: hidden;
}
.background-loop-video {
  display: block;
}
.background-loop-video:before {
  background-image: linear-gradient(
    180deg,
    #0c0c0c,
    hsla(0, 0%, 5%, 0) 20%,
    hsla(0, 0%, 5%, 0) 67%,
    #0c0c0c 98%
  );
  bottom: 0;
  content: '';
  display: block;
  left: 0;
  opacity: 0.7;
  position: absolute;
  right: 0;
  top: 0;
  z-index: 1;
}
.fullscreen-bg-video {
  height: auto;
  left: 50%;
  min-height: 100%;
  min-width: 100%;
  overflow: hidden;
  pointer-events: none;
  position: absolute;
  top: 50%;
  transform: translateX(-50%) translateY(-50%);
  width: auto;
  z-index: 0;
}
</style>
<script setup></script>
