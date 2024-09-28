<template>
  <footer
    class="bg-neutral-100 dark:bg-zinc-800/80 w-full border-t border-neutral-200"
  >
    <div
      :class="
        cn(
          'flex flex-col gap-2 py-6 shrink-0 items-center px-4 md:px-6 text-gray-500 dark:text-gray-400 text-sm'
        )
      "
    >
      <p>
        KeplerPlanner is 100% free and Open Source project under the
        <NuxtLink
          to="https://github.com/mitsimi/keplerPlanner/blob/main/LICENSE"
          class="text-[#00B0FF] inline-flex items-center space-x-1"
        >
          <p>MIT license</p>
          <ArrowTopRightOnSquareIcon
            class="h-[14px] w-[14px] inline"
          /> </NuxtLink
        >.
      </p>
      <p>Copyright © 2024-present mitsimi and contributors.</p>
    </div>
  </footer>
</template>

<script setup>
import { cn } from "@/lib/utils";
import { ArrowTopRightOnSquareIcon } from "@heroicons/vue/24/outline";
</script>
