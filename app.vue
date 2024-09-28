<script setup lang="ts">
import { SpeedInsights } from "@vercel/speed-insights/vue";
</script>

<template>
  <Navbar class="bg-neutral-100/80 dark:bg-zinc-800/80 backdrop-blur" />
  <NuxtPage class="dark:bg-zinc-800" />
  <Footer />
  <SpeedInsights />
</template>
