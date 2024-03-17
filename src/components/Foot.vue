<template>
  <div class="bg-[#F8F9FA] py-10">
    <div class="max-w-sm sm:max-w-lg m-auto">
      <div class="flex flex-col sm:flex-row">
        <div class="flex items-center flex-col sm:items-start sm:w-1/3">
          <div class="flex flex-shrink-0 items-center">
            <img class="h-16 w-auto" src="/logo.png" alt="Logo" />
            <span class="ml-2 font-bold text-[2rem]">inTinker</span>
          </div>
          <p>3D Printing Calibrations Powered by AI</p>
        </div>
        <div class="flex items-center flex-col sm:w-1/3">
          <p class="font-bold leading-8">
            Start a Calibration Today
          </p>
          <p class="leading-8">Don't wait to start printing a better material for you project.</p>
          <button
            class="bg-regal-orange text-white text-opacity-[0.85] hover:text-opacity-100 text-[20px] font-bold py-2 px-8 mt-2 rounded-lg">
            Start Calibration for FREE
          </button>
        </div>
        <div class="text-center sm:w-1/3 sm:text-right flex flex-col">
          <p class="font-bold leading-8 mt-[50px] sm:mt-0">Company</p>
          <p class="leading-8 mt-[50px] sm:mt-0 cursor-pointer" @click="handleClickFeatures('section6')">Features</p>
          <p class="leading-8 cursor-pointer" @click="handleClickFeatures('section8')">Pricing</p>
          <p class="leading-8 cursor-pointer" @click="handleClickFeatures('section10')">About</p>
          <a href="https://www.intinker.com/blog" target="_blank" class="leading-8 cursor-pointer">Blog</a>
          <a href="https://www.intinker.com/termsandconditions" target="_blank" class="leading-8">Terms and
            Conditions</a>
        </div>
      </div>
    </div>
  </div>
  <div class="bg-[#EBECED] py-2">
    <p class="text-[#667085] text-[18px] text-center">2023 Copyright: intinker.com</p>
  </div>
</template>
<script lang="ts" setup>
import { createScrollRevealDirective } from 'vue-scroll-reveal';
const vScrollReveal = createScrollRevealDirective({
  class: 'v-scroll-reveal',
  delay: 500,
  duration: 1500,
  distance: '80px',
  reset: 'false',
  opacity: 0,
});
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