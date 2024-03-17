<template>
  <div class="max-w-sm sm:max-w-lg m-auto mt-[200px] mb-[100px] relative" id="section7" v-on:scroll="handleScroll"
    v-scroll-reveal.reset="{ origin: 'left', distance: '30px' }">
    <div class="sticky top-0 bg-white z-40 p-2">
      <div class="font-Roboto font-bold text-[30px] hidden sm:block">
        # HOW IT WORKS
      </div>
      <div class="font-Roboto font-bold text-[30px] sm:hidden">
        # HOW THE SOFTWARE WORKS
      </div>
      <div class="font-bold text-sm text-black text-opacity-60 max-w-screen-lg sticky">
        Below takes you through a step by step example of what its like using inTinker to dial in a new material.
      </div>
    </div>
    <div class="mt-10 flex">
      <Timeline :handleTab="handleTabClick" class="sm:w-1/2 " />
      <CImageScroll />
      <!-- <CImage /> -->
    </div>
  </div>
</template>


<script lang="ts" setup>
import Timeline from './Timeline.vue';
import CImageScroll from './CImageScroll.vue';
// import CImage from './CImage.vue';

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
    handleTabClick(tab: String) {
      this.handleTab(tab);
    }
  }
}
</script>
