<script lang="ts" setup>
import Navigation from './components/Navigation.vue'
import HeroSection from './components/HeroSection.vue'
import Section1 from './components/Section1.vue'
import Section2 from './components/Section2.vue'
import Section3 from './components/Section3.vue'
import Section4 from './components/Section4.vue'
import Section5 from './components/Section5.vue'
import Section6 from './components/Section6.vue'
import Section7 from './components/Section7.vue'
import Section71 from './components/Section7-1.vue'
import Section8 from './components/Section8.vue'
import Section9 from './components/Section9.vue'
import Section10 from './components/Section10.vue'
// import CImage from './components/CImage.vue'
import Foot from './components/Foot.vue'
</script>

<script lang="ts">
export default {
  data() {
    return {
      current: 'tab1'
    }
  },
  methods: {
    handleTab(tab: string) {
      // console.log("tab: ", tab);
      this.current = tab;
    },

  },

}

</script>

<template>
  <Navigation />
  <HeroSection />
  <!-- <CImage /> -->
  <Section1 />
  <Section2 />
  <div :class="$style.bgGrad" class="text-white mt-[300px] py-10">
    <Section3 />
    <Section4 />
    <Section5 :handleTab="handleTab" />
  </div>
  <Section6 :currentTab="current" :handleTab="handleTab" />
  <Section7 :handleTab="handleTab" />
  <Section71 />
  <Section8 />
  <Section9 />
  <Section10 />
  <Foot />
</template>

<style module>
.bgGrad {
  background: radial-gradient(50% 50% at 50% 50%,
      #010000,
      #050404 18.09%,
      #070606 41.59%,
      #2a2a2e)
}
</style>