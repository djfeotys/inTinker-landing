<template>
  <div class="flex">
    <img src="/timeline.svg" class="mt-2 hidden sm:block"
      v-scroll-reveal.reset="{ origin: 'top', delay: 200, distance: '30px' }" />
    <div class="ml-4">
      <div class="font-bold text-[24px] text-black text-opacity-[0.85] ml-4">Create Assets</div>
      <div class="bg-[#F8F8F8] rounded-lg px-4 py-2 sm:mt-[120px]">
        <p class="font-bold text-[16px] text-opacity-[0.85]">Printer and Material</p>
        <p class="text-[14px] max-w-[460px] text-black text-opacity-60">Select a pre configured printer and material, If
          we dont have what your
          looking for
          you can define a
          custom printer or material with any build plate size, start end gcode, print temperature range and many
          more options.</p>
      </div>
      <img src="/img(sec7-1-mobile).svg" class="w-full sm:hidden" />
      <div class="sm:mt-[200px] ml-4">
        <p class="font-bold text-[16px]">Print Profile</p>
        <p class="text-[14px] max-w-[460px] text-black text-opacity-60">Create a print profile using any combination of
          printer, material and
          nozzle size. </p>
      </div>
      <img src="/img(sec7-2).svg" class="w-full sm:hidden" />
      <div class="font-bold text-[24px] sm:mt-[550px] ml-4">Run Calibration</div>
      <div class="sm:mt-[70px] ml-4">
        <p class="font-bold text-[16px]">Start a Calibration</p>
        <div class="text-[14px] max-w-[420px]">
          <p class="text-black text-opacity-60">
            Start a calibration from the Print Profile you just created. This
            calibration will be linked to that Print Profile.
          </p>
          <a @click="handleClick('tab1')" style="color:#F3762B; border-bottom: 1px solid;"
            class="border-regal-orange cursor-pointer">
            Learn More about Print Profiles >
          </a>
        </div>
      </div>
      <img src="/img(sec7-3).svg" class="mb-[100px] w-full rounded shadow-lg mt-5 sm:hidden"
        style="border: 1px solid #e5e5e5;" />
      <div class="sm:mt-[190px] ml-4">
        <p class="font-bold text-[16px]">Add Prints</p>
        <div class="text-[14px] max-w-[420px]">
          <p class="text-black text-opacity-60">
            A calibration is split up into a number of Prints. There can be any number of prints in a
            calibration including a mixture of Freestyle and AI Prints.
          </p>
          <a @click="handleClick('tab3')" class="cursor-pointer" style="color:#F3762B;border-bottom: 1px solid;">
            Learn More about Calibration Prints >
          </a>
        </div>
      </div>
      <img src="/img(sec7-4).svg" class="mb-[50px] w-full rounded shadow-lg mt-5  sm:hidden" />
      <div class="sm:mt-[250px] ml-4">
        <p class="font-bold text-[16px]">Print and Score Quality</p>
        <div class="text-[14px] max-w-[420px]">
          <p class="text-black text-opacity-60">
            Score the quality of stringing and under extrusion from 1-10. 1 being a failed print and 10 being
            perfect quality. These scores are what the algorithm uses to determine the next set of settings to
            you.
          </p>
          <a style="color:#F3762B;border-bottom: 1px solid;">
            Open Scoring Guide >
          </a>
        </div>
      </div>
      <img src="/img(sec7-5).svg" class="mb-[50px] w-full rounded shadow-lg mt-5 sm:hidden" />
      <div class="sm:mt-[350px] ml-4">
        <p class="font-bold text-[16px]">Repeat</p>
        <div class="text-[14px] max-w-[420px]">
          <p class="text-black text-opacity-60">
            As you add and score more prints the AI refines its model customized for your printer, material and
            nozzle size. Typically after around 5-7 prints users see satisfactory results. Its also common that
            we get it on the first or second print.
          </p>
        </div>
      </div>
      <img src="/img(sec7-6).svg" class="mb-[50px] w-full rounded shadow-lg mt-5 sm:hidden" />
      <div class="sm:mt-[380px] ml-4">
        <p class="font-bold text-[24px]">Export Settings to Cura</p>
        <div class="text-[14px] max-w-[420px]">
          <p class="text-black text-opacity-60">
            Once you have settings that work well, you can export them to use for anything you want. The Print
            Level you export update the print profile the calibration is in, so later you can simply re download
            that print profile to use these settings again.
          </p>
        </div>
      </div>
      <img src="/img(sec7-7).svg" class="w-full mt-5 sm:hidden" />
    </div>
  </div>
</template>

<script lang="ts" setup>
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
    handleClick(tab: String) {
      this.handleTab(tab);
      const htmlDocument: Document = document;
      const position = htmlDocument.getElementById("section6").offsetTop;
      // smooth scroll
      window.scrollTo({ top: position, behavior: "smooth" });
    }
  }
}
</script>