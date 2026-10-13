<template>
  <Provider v-if="!isDesktopLyric">
    <router-view />
  </Provider>
  <router-view v-else />
  <Analytics />
  <SpeedInsights />
</template>

<script setup lang="ts">
import { Analytics } from "@vercel/analytics/vue";
import { SpeedInsights } from "@vercel/speed-insights/vue";

const isDesktopLyric = location.hash.includes("desktop-lyric");
</script>
