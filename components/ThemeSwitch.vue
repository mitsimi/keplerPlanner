<template>
  <Button variant="ghost" size="icon" @click="toggleTheme">
    <span class="sr-only">Toggle Theme</span>
    <div class="flex flex-row items-center justify-center">
      <div class="">
        <span v-if="colorMode.preference === 'light'" class="theme-icon">
          <IconLightMode />
        </span>
        <span v-else-if="colorMode.preference === 'dark'" class="theme-icon">
          <IconDarkMode />
        </span>
        <span v-else class="theme-icon">
          <IconLightMode class="text-neutral-400/75 dark:text-neutral-300/50" />
        </span>
      </div>
    </div>
  </Button>
</template>

<script lang="ts" setup>
import { ref } from "vue";

let idx: number;
const modes: string[] = ["system", "light", "dark"];

const colorMode = ref(useColorMode());
idx = modes.findIndex((v) => v === colorMode.value.preference);
colorMode.value.preference = modes[idx % modes.length];

const toggleTheme = () => {
  idx++;
  colorMode.value.preference = modes[idx % modes.length];
  console.log(colorMode.value.preference);
};
console.log(colorMode.value.preference);
</script>

<style scoped>
.theme-icon {
  @apply w-7 h-7 cursor-pointer;
}
</style>
