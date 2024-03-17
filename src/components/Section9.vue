<template>
	<div class="max-w-sm sm:max-w-lg m-auto mt-[150px] mb-[100px]"
		v-scroll-reveal.reset="{ origin: 'left', distance: '30px' }">
		<div>
			<p class="font-Roboto font-bold text-[30px] text-center">
				Frequently Asked Questions
			</p>
			<p class="font-Roboto text-[14px] text-center">Everything you need to know about the product and billing.</p>
		</div>
		<CAccordion />
	</div>
</template>
<script lang="ts" setup>
import CAccordion from './CAccordion.vue';
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