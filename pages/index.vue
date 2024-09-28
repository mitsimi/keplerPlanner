<script setup>
import { cn } from "@/lib/utils";
import {
  ChartBarIcon,
  ShieldCheckIcon,
  WindowIcon,
} from "@heroicons/vue/24/outline";
</script>

<template>
  <main class="flex flex-col items-center space-y-48 md:space-y-32">
    <!-- Hero -->
    <section class="w-full pt-48 xl:pt-60 grid justify-center">
      <div class="container px-4 md:px-6">
        <div class="flex flex-col items-center space-y-6 text-center">
          <h1
            class="text-3xl sm:text-4xl md:text-5xl lg:text-6xl/none font-bold tracking-tighter md:[word-spacing:_10px] text-balanced"
          >
            A new way of
            <br />
            <span class="bg-clip-text text-transparent bg-[#00B0FF]"
              >planning
            </span>
            your semester
          </h1>
          <p
            class="mx-auto max-w-[700px] text-gray-500 md:text-xl dark:text-gray-400 md:text-balance"
          >
            Save time and nerves with this new application. Plan faster than
            ever before and get a better overview of your schedule.
          </p>

          <!-- Buttons-->
          <div class="space-x-4">
            <Button asChild variant="primary" class="bg-[#00B0FF] text-white">
              <NuxtLink to="/plan">Get Started</NuxtLink>
            </Button>
            <Button
              variant="outline"
              class="border-2 dark:border-white dark:bg-neutral-800"
            >
              <NuxtLink to="https://github.com/mitsimi">
                View on Github
              </NuxtLink>
            </Button>
          </div>
        </div>
      </div>
    </section>

    <!-- Key Features -->
    <section class="w-full grid justify-center">
      <div class="container p-8 md:p-12 rounded-md flex flex-col">
        <h2
          class="text-3xl font-bold tracking-tighter sm:text-5xl mb-8 text-center z-10"
        >
          Key Features
        </h2>
        <div
          :class="
            cn(
              'grid gap-10 sm:grid-cols-2 md:grid-cols-3',
              'sm:*:[&:last-child]:col-span-full md:*:[&:last-child]:col-span-1',
              '*:shadow-[20px_20px_60px_#bebebe,_-20px_-20px_60px_#ffffff] dark:*:shadow-[20px_20px_60px_#1f1f1f,_-20px_-20px_60px_#292929] *:border-0'
            )
          "
        >
          <Card class="group">
            <CardContent class="flex flex-col items-center space-y-2 p-6">
              <WindowIcon class="h-12 w-12 mb-2" />
              <h3 class="text-xl font-bold">
                <span
                  :class="
                    cn(
                      'relative before:absolute before:bottom-0 before:h-2 before:w-0 before:items-end before:translate-y-1',
                      'before:bg-gradient-to-r before:from-sky-400/50 before:via-sky-500/30',
                      'before:motion-reduce::transition-none before:transition-all',
                      'before:duration-200 ease-out group-hover:before:w-full'
                    )
                  "
                >
                  Intuitive Design
                </span>
              </h3>
              <p
                class="text-sm text-gray-500 dark:text-gray-400 text-center text-balance md:text-wrap xl:text-balance"
              >
                Our user-friendly interface ensures a smooth experience for all
                users.
              </p>
            </CardContent>
          </Card>

          <Card class="group">
            <CardContent class="flex flex-col items-center space-y-2 p-6">
              <ShieldCheckIcon class="h-12 w-12 mb-2" />
              <h3 class="text-xl font-bold">
                <span
                  :class="
                    cn(
                      'relative before:absolute before:bottom-0 before:h-2 before:w-0 before:items-end before:translate-y-1',
                      'before:bg-gradient-to-r before:from-sky-400/50 before:via-sky-500/30',
                      'before:motion-reduce::transition-none before:transition-all',
                      'before:duration-200 ease-out group-hover:before:w-full'
                    )
                  "
                >
                  Privacy
                </span>
              </h3>
              <p
                class="text-sm text-gray-500 dark:text-gray-400 text-center text-balance md:text-wrap xl:text-balance"
              >
                We do not store any kind of information about the user, nor do
                we collect telemetry.
              </p>
            </CardContent>
          </Card>

          <Card class="group">
            <CardContent class="flex flex-col items-center space-y-2 p-6">
              <ChartBarIcon class="h-12 w-12 mb-2" />
              <h3 class="text-xl font-bold text-center">
                <span
                  :class="
                    cn(
                      'relative before:absolute before:bottom-0 before:h-2 before:w-0 before:items-end before:translate-y-1',
                      'before:bg-gradient-to-r before:from-sky-400/50 before:via-sky-500/30',
                      'before:motion-reduce::transition-none before:transition-all',
                      'before:duration-200 ease-out group-hover:before:w-full'
                    )
                  "
                >
                  Always up-to-date
                </span>
              </h3>
              <p
                class="text-sm text-gray-500 dark:text-gray-400 text-center text-balance md:text-wrap xl:text-balance"
              >
                Always have the latest courses so you can plan accordingly.
              </p>
            </CardContent>
          </Card>
        </div>
      </div>
    </section>

    <!-- Get started now -->
    <section class="w-full pb-36 md:pb-48 xl:pb-60 grid justify-center">
      <div class="container px-4 md:px-6">
        <div class="flex flex-col items-center space-y-4 text-center">
          <div class="space-y-2">
            <h2 class="text-3xl font-bold tracking-tighter sm:text-5xl">
              Ready to Get Started?
            </h2>
            <p
              class="mx-auto max-w-[600px] text-gray-500 md:text-xl/relaxed lg:text-base/relaxed xl:text-xl/relaxed dark:text-gray-400"
            >
              We&apos;ve helped thousands of students like you to get on top of
              their schedules! Join the ranks and discover how this tool can
              speed up your schedule planning!
            </p>
          </div>
          <div class="w-full max-w-sm space-y-2">
            <Button class="w-full">
              <NuxtLink class="w-full" to="/plan">
                Plan your next semester
              </NuxtLink>
            </Button>
            <!--p class="text-xs text-gray-500 dark:text-gray-400">
              By subscribing, you agree to our Terms of Service and Privacy
              Policy.
            </p-->
          </div>
        </div>
      </div>
    </section>
  </main>
</template>
