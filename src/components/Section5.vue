<template>
  <div class="flex flex-row justify-center my-[130px]" v-scroll-reveal.reset="{ origin: 'left', distance: '30px' }">
    <div class="max-w-sm sm:max-w-lg mt-20 flex flex-col items-center">
      <p class="font-Roboto font-bold text-md text-center">How does AI help you?</p>
      <p class="font-Roboto text-sm">Learn more about how inTinker uses AI to help you in its calibrations.</p>
      <button
        class=" bg-white text-black text-opacity-[0.85] hover:text-opacity-100 text-xl font-bold py-4 px-4 rounded-lg mt-5 flex items-center"
        @click="handleClick">
        Learn more About AI
        <img src="/wand.svg" class="ml-2" />
      </button>
      <div class="flex flex-row mt-4">
        <StarIcon class="h-7 w-7 text-yellow-300" />
        <StarIcon class="h-7 w-7 text-yellow-300" />
        <StarIcon class="h-7 w-7 text-yellow-300" />
        <StarIcon class="h-7 w-7 text-yellow-300" />
        <StarIcon class="h-7 w-7 text-yellow-300" />
      </div>
      <p class="max-w-[420px] text-center mt-2 font-Roboto">"Thanks for this incredible tool, this tool has blown me away.
        I've been
        able
        to solve an
        issue with my prints
        after months of struggling."
      </p>
      <img src="/img(sec5).svg" class="mt-4" />
    </div>
  </div>
</template>
<script lang="ts" setup>
import { StarIcon } from '@heroicons/vue/24/solid';
import { createScrollRevealDirective } from 'vue-scroll-reveal';
const vScrollReveal = createScrollRevealDirective({
  class: 'v-scroll-reveal',
  delay: 500,
  duration: 1500,
  distance: '80px',
  reset: false,
  opacity: 0,
});
</script>

<script lang="ts">
export default {
  props: {
    handleTab: { type: Function }
  },
  methods: {
    handleClick() {
      this.handleTab("tab4");
      const htmlDocument: Document = document;
      const position = htmlDocument.getElementById("section6").offsetTop;
      // smooth scroll
      window.scrollTo({ top: position, behavior: "smooth" });
    }
  }
}
</script>