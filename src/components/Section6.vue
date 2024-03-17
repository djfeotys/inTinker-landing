<template>
  <div class="max-w-sm sm:max-w-lg m-auto mt-[150px] mb-[100px]" id="section6">
    <div class="font-Roboto font-bold text-[30px]">
      # FEATURES
    </div>
    <div class="text-black text-opacity-60 max-w-[800px] text-[15px] mb-[40px] font-bold">
      Discover the key features that inTinker offers for your 3D printing tasks. Our tools make tuning new materials
      simple, ensuring a smooth transition every time. From auto-calibration to easy analysis, explore what makes
      inTinker a handy companion for your 3D printing projects.
    </div>
    <CTab :current="currentTab" :handleTab="handleTab" />
  </div>
</template>
<script lang="ts" setup>
import CTab from './CTab.vue';
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
    currentTab: { type: String },
    handleTab: { type: Function }
  }
}
</script>