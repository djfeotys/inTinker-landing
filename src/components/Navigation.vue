<template>
  <Disclosure as="nav" v-slot="{ open }" class="max-w-sm sm:max-w-lg m-auto mt-6 "
    v-scroll-reveal.reset="{ origin: 'top', distance: '30px' }" @scroll="handleScroll">
    <div class="mt-6 relative">
      <div class="relative flex h-16 items-center justify-between fix">
        <div class="absolute inset-y-0 right-0 flex items-center sm:hidden">
          <!-- Mobile menu button-->
          <DisclosureButton
            class="relative inline-flex items-center justify-center rounded-md p-2 text-gray-400 hover:bg-gray-700 hover:text-white focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white">
            <!-- <span class="absolute -inset-0.5"></span>
            <span class="sr-only">Open main menu</span> -->
            <Bars3Icon v-if="!open" class="block h-10 w-10" aria-hidden="true" />
            <XMarkIcon v-else class="block h-6 w-6" aria-hidden="true" />
          </DisclosureButton>
        </div>
        <div class="flex flex-1 sm:items-stretch justify-start">
          <div class="flex flex-shrink-0 items-center">
            <img class="h-16 w-auto" src="/logo.png" alt="Logo" />
            <span class="ml-2 font-bold text-[2rem]">inTinker</span>
          </div>
        </div>
        <div class="absolute inset-y-0 right-0 flex items-center pr-2 sm:static sm:inset-auto sm:ml-6 sm:pr-0">
          <div class="hidden sm:ml-6 sm:block">
            <div class="flex space-x-4">
              <a v-for="item in navigation" :key="item.name" @click="handleClickFeatures(item.id)" :href="item.href"
                target="_blank"
                :class="[item.current ? 'cursor-pointer bg-regal-orange text-white hover:text-opacity-100 px-10' : 'cursor-pointer px-5 text-black hover:bg-regal-orange hover:text-white', 'rounded-md py-2 text-[1.3rem] text-opacity-[0.85] font-medium']"
                :aria-current="item.current ? 'page' : undefined">{{ item.name }}</a>
            </div>
          </div>
        </div>
      </div>
    </div>

    <DisclosurePanel class="sm:hidden">
      <div class="space-y-1 px-2 pb-3 pt-2">
        <DisclosureButton v-for="item in navigation" :key="item.name" as="a" @click="handleClickFeatures(item.id)"
          :href="item.href" :target="target"
          :class="[item.current ? 'bg-regal-orange text-white' : 'text-gray-300 hover:bg-gray-700 hover:text-white cursor-pointer', 'cursor-pointer block rounded-md px-3 py-2 text-base font-medium']"
          :aria-current="item.current ? 'page' : undefined">{{ item.name }}</DisclosureButton>
      </div>
    </DisclosurePanel>
  </Disclosure>
</template>
  
<script lang="ts" setup>
import { Disclosure, DisclosureButton, DisclosurePanel } from '@headlessui/vue'
import { Bars3Icon, XMarkIcon } from '@heroicons/vue/24/outline'
import { createScrollRevealDirective } from 'vue-scroll-reveal';
const vScrollReveal = createScrollRevealDirective({
  class: 'v-scroll-reveal',
  delay: 200,
  duration: 1000,
  distance: '80px',
  reset: 'false',
  opacity: 0,
});

const navigation = [
  { name: 'Features', id: 'section6', current: false },
  { name: 'Pricing', id: 'section8', current: false },
  { name: 'Blog', href: 'https://www.intinker.com/blog', target: "_blank", current: false },
  { name: 'About', id: 'section10', current: false },
  { name: 'Sign in', href: 'https://intinker.com/Identity/Account/Login', current: true },
]
</script>

<script lang="ts">
export default {
  methods: {
    handleClickFeatures(id: String) {
      const htmlDocument: Document = window.document;
      const position = htmlDocument.getElementById(id).offsetTop;
      // smooth scroll
      window.scrollTo({ top: position, behavior: "smooth" });
    }
  }
}
</script>