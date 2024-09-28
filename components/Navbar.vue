<script lang="ts" setup>
import { Disclosure, DisclosureButton, DisclosurePanel } from "@headlessui/vue";
import { Bars3Icon, XMarkIcon } from "@heroicons/vue/24/solid";
import { cn } from "@/lib/utils";

type Link = {
  label: string;
  href: string;
};
const links: Link[] = [
  { label: "Home", href: "/" },
  { label: "Planner", href: "/plan" },
  { label: "About", href: "/about" },
];
const socials: Map<string, Link> = new Map([
  [
    "github",
    { label: "Github", href: "https://github.com/mitsimi/keplerPlanner" },
  ],
]);
</script>

<template>
  <Disclosure
    as="header"
    v-slot="{ open }"
    class="z-50 fixed top-0 right-0 left-0"
  >
    <div class="py-4">
      <div class="flex justify-between">
        <!-- Branding -->
        <div class="shrink-0 flex items-center">
          <div class="flex items-center mx-4 space-x-2">
            <svg
              fill="currentColor"
              viewBox="0 0 16 16"
              height="2em"
              width="2em"
            >
              <path
                fillRule="evenodd"
                d="M.11 3.187A.5.5 0 01.5 3h13a.5.5 0 01.488.608l-.22.991a3.001 3.001 0 01-1.3 5.854l-.132.59A2.5 2.5 0 019.896 13H4.104a2.5 2.5 0 01-2.44-1.958L.012 3.608a.5.5 0 01.098-.42zm12.574 6.288a2 2 0 00.866-3.899l-.866 3.9zM1.124 4l1.516 6.825A1.5 1.5 0 004.104 12h5.792a1.5 1.5 0 001.464-1.175L12.877 4H1.123z"
              />
            </svg>
            <span class="text-lg font-semibold tracking-wide"
              >KeplerPlanner</span
            >
          </div>
        </div>
        <!-- Links | Theme | Socials -->
        <div class="grow-1 mx-4">
          <!-- Desktop View -->
          <div :class="cn('hidden md:flex justify-end items-center space-x-4')">
            <!-- Desktop Links -->
            <div class="flex items-center">
              <ul
                class="hidden md:flex flex-wrap items-center justify-center space-x-1 list-none"
              >
                <li v-for="link in links">
                  <NuxtLink
                    :to="link.href"
                    :class="
                      cn(
                        'inline-flex items-center justify-center rounded px-3 py-1.5',
                        'text-sm font-semibold md:text-lg',
                        'hover:bg-gray-200 hover:text-gray-900 focus:bg-gray-200 focus:text-gray-900 focus:outline-none active:bg-gray-300'
                      )
                    "
                  >
                    {{ link.label }}
                  </NuxtLink>
                </li>
              </ul>
            </div>

            <!-- Theme Toggle -->
            <div
              :class="
                cn(
                  'before:absolute before:mx-2 before:w-[1px] before:h-6',
                  'before:translate-y-2 before:-translate-x-[16px]',
                  'before:rounded-full before:bg-neutral-200 before:dark:bg-neutral-600'
                )
              "
            >
              <ThemeSwitch />
            </div>

            <!-- Socials -->
            <div
              :class="
                cn(
                  'before:absolute before:mx-2 before:w-[1px] before:h-6',
                  'before:translate-y-2 before:-translate-x-[16px]',
                  'before:rounded-full before:bg-neutral-200 before:dark:bg-neutral-600'
                )
              "
            >
              <!-- Github Button -->
              <NuxtLink :to="socials.get('github')!.href">
                <span class="sr-only">Link to source code on Github</span>
                <Button variant="ghost" size="icon">
                  <IconGithub />
                </Button>
              </NuxtLink>
            </div>
          </div>
          <!-- Mobile View -->
          <div class="md:hidden flex justify-end items-center">
            <!-- Theme Toggle -->
            <ThemeSwitch />

            <!-- Menu Burger -->
            <DisclosureButton
              class="group relative inline-flex items-center justify-center rounded-md p-2"
            >
              <span class="sr-only">Open main menu</span>
              <Bars3Icon
                aria-hidden="true"
                class="h-6 w-6"
                :class="open && 'hidden'"
              />
              <XMarkIcon
                aria-hidden="true"
                class="h-6 w-6"
                :class="(open && 'block') || 'hidden'"
              />
            </DisclosureButton>
          </div>
        </div>
      </div>
    </div>
    <Transition
      enter-active-class="transition-all duration-200"
      enter-from-class="opacity-0 -translate-y-2"
      enter-to-class="opacity-80"
      leave-active-class="transition-all duration-200"
      leave-from-class="opacity-100 "
      leave-to-class="opacity-0 -translate-y-2"
      mode="in-out"
    >
      <DisclosurePanel
        :class="
          cn(
            'px-5',
            'rounded-b-md shadow-md z-40 bg-neutral-50/85 dark:bg-neutral-800/80 backdrop-blur-md'
          )
        "
      >
        <div class="flex flex-col space-y-1 px-2 pb-3 pt-2 divide-y">
          <!-- Navigation Links -->
          <nav>
            <NuxtLink v-for="link in links" :to="link.href">
              <DisclosureButton
                class="w-full px-3 py-2 flex flex-col items-center rounded-md hover:bg-gray-200 hover:text-gray-900 dark:hover:bg-neutral-800 dark:hover:text-foreground focus:bg-gray-200 focus:text-gray-900 focus:outline-none active:bg-gray-300"
              >
                <span
                  class="rounded-md text-base font-semibold hover:focus:underline underline-offset-4 decoration-2"
                >
                  {{ link.label }}
                </span>
              </DisclosureButton>
            </NuxtLink>
          </nav>

          <!-- Socials -->
          <div>
            <NuxtLink :to="socials.get('github')!.href">
              <DisclosureButton
                class="w-full px-3 py-2 flex flex-col items-center rounded-md hover:bg-gray-200 hover:text-gray-900 dark:hover:bg-neutral-800 dark:hover:text-foreground focus:bg-gray-200 focus:text-gray-900 focus:outline-none active:bg-gray-300"
              >
                <span
                  class="rounded-md text-base font-semibold hover:focus:underline underline-offset-4 decoration-2"
                >
                  {{ socials.get("github")!.label }}
                </span>
              </DisclosureButton>
            </NuxtLink>
          </div>
        </div>
      </DisclosurePanel>
    </Transition>
  </Disclosure>
</template>
