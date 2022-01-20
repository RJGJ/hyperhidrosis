<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from "vue";
import videojs, { VideoJsPlayer, VideoJsPlayerOptions } from "video.js";

import 'video.js/dist/video-js.min.css';

const videoOptions = ref<VideoJsPlayerOptions>({
  controls: true,
  preload: "none",
  width: 300,
  height: 600,
  poster: "assets/img/Screenshot_1.jpg",
  sources: [
    {
      src: "assets/videos/video.mp4",
      type: "video/mp4",
    },
  ],
});
const videoPlayer = ref(null);
let vjs: VideoJsPlayer | null = null;

onMounted(() => {
  vjs = videojs('#video-player', videoOptions.value, () => {
    console.log("video player ready");
  });
});

onBeforeUnmount(() => {
  if (vjs) vjs.dispose();
});
</script>

<template>
  <video
    ref="videoPlayer"
    id="video-player"
    class="video-js vjs-default-skin vjs-big-play-centered"
  ></video>
</template>
