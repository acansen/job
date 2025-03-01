<template>
  <div class="bannar">
    <div class="background-loop-video">
      <video
        ref="bgVideo"
        autoplay
        loop
        muted
        playsinline
        class="fullscreen-bg-video"
        poster="video.webp"
      >
        <!-- <source src="mobile.webm" type="video/mp4" media="(max-width: 575px)" />
        <source src="pc.webm" type="video/mp4" /> -->
      </video>
    </div>
    <!-- <div class="full-width justify-end container">
      <div class="bg-yellow" style="height: 5rem"></div>
    </div> -->
  </div>
</template>
<script setup>
import { ref, onMounted } from 'vue'
// import { useQuasar } from 'quasar'
// const $q = useQuasar()
const bgVideo = ref(null)
// const videoSrc = $q.screen.width < 575 ? 'pc.webm' : 'pc.webm'
const videoSrc = 'pc.webm'
onMounted(() => {
  if (!('playsInline' in bgVideo.value)) {
    console.log('不支持视频同层播放')
  }
  const video = bgVideo.value
  let mediaSource = new MediaSource()
  video.src = URL.createObjectURL(mediaSource)
  mediaSource.addEventListener('sourceopen', sourceOpen)
  async function sourceOpen() {
    // const sourceBuffer = mediaSource.addSourceBuffer('video/mp4; codecs="avc1.640028"')
    const sourceBuffer = mediaSource.addSourceBuffer('video/webm; codecs="vp9"') // vp8, opus, vorbis
    sourceBuffer.addEventListener('updateend', () => {
      video.play()
      mediaSource.endOfStream()
    })
    await fetch(videoSrc)
      .then((response) => response.arrayBuffer())
      .then((data) => {
        console.log(data, 123)

        sourceBuffer.appendBuffer(data)
      })
      .catch((error) => {
        console.error('Error fetching video:', error)
      })
  }
})
</script>
<style scoped>
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

.bannar {
  border: solid transparent;
  border-width: 0 0 50px;
  height: calc(100vh - 80px);
  max-height: 840px;
  overflow: hidden;
  position: relative;
  width: 100%;
}

@media screen and (min-width: 992px) {
  .bannar {
    min-height: 780px;
  }
}

@media screen and (max-width: 991px) {
  .bannar {
    border-width: 0 0 30px;
    height: calc(60vh - 80px);
    min-height: 600px;
  }
}

@media screen and (max-width: 575px) {
  .bannar {
    border-width: 0;
    height: 80vh;
    max-height: none;
    min-height: 410px;
    padding-top: 0;
  }
}

@media only screen and (max-width: 991px) and (orientation: landscape) {
  .bannar {
    height: calc(100vh - 80px);
    min-height: 600px;
  }
}

@media screen and (max-width: 575px) and (min-height: 1300px) {
  .bannar {
    height: 41rem;
  }
}

.bannar .container {
  display: flex;
  flex-direction: column;
  height: 100%;
  padding-bottom: 80px;
  padding-top: 80px;
  position: relative;
  z-index: 1;
}

@media screen and (max-width: 991px) {
  .bannar .container {
    padding-bottom: 40px;
    padding-top: 40px;
  }
}
</style>
