<template>
	<div id="accordion-collapse" class="divide-y divide-gray-100 divide-solid ">
		<h2 id="accordion-collapse-heading-1">
			<button type="button"
				class="flex items-center justify-between w-full p-5 font-medium rtl:text-right text-gray-500 gap-3"
				@click="handleClick('btn1')">
				<span class="font-bold">Requirements</span>
				<img :src="current === 'btn1' ? '/Icon-minus.svg' : '/Icon-pluse.svg'">
			</button>
		</h2>
		<div id="accordion-collapse-body-1" :class="current === 'btn1' ? '' : 'hidden'">
			<div class="p-5 text-[#667085]">
				<p class="mb-2">- Printer must be in sound mechanical order</p>
				<p>- Material must be in good printing condition. Not soaking wet
					or stale</p>
				<p class="mb-2">- Must be an FDM/FFF printer (cartesian only, no delta
					printers, yet)</p>
				<p class="mb-2">- No dual extrusion, yet</p>
				<p class="mb-2">- 0.2mm layer height, for now</p>
				<p class="mb-2">- Only marlin Firmware</p>
				<p class="mb-2">- Can use custom start/end gcode</p>
				<p class="mb-2">- Cura 4.8.0+ only, *for now (*Newer version seem to work,
					but are not as rigorously tested)</p>
			</div>
		</div>
		<h2 id="accordion-collapse-heading-2">
			<button type="button"
				class="flex items-center justify-between w-full p-5 font-medium rtl:text-right text-gray-500 gap-3"
				@click="handleClick('btn2')">
				<span>What is your cancellation policy?</span>
				<img :src="current === 'btn2' ? '/Icon-minus.svg' : '/Icon-pluse.svg'">
			</button>
		</h2>
		<div id="accordion-collapse-body-2" :class="current === 'btn2' ? '' : 'hidden'">
			<div class="p-5 text-[#667085]">
				<p class="mb-2">- To cancel your plan, simply navigate to your profile in the upper right corner of
					Dashboard. Select the Customer portal and click Cancel. You are also entitled to a refund if you are not
					satisfied.
				</p>
			</div>
		</div>
		<h2 id="accordion-collapse-heading-3">
			<button type="button"
				class="flex items-center justify-between w-full p-5 font-medium rtl:text-right text-gray-500 gap-3"
				@click="handleClick('btn3')">
				<span>How does the Trial work?</span>
				<img :src="current === 'btn3' ? '/Icon-minus.svg' : '/Icon-pluse.svg'">
			</button>
		</h2>
		<div id="accordion-collapse-body-3" :class="current === 'btn3' ? '' : 'hidden'">
			<div class="p-5">
				<p class="mb-2">You have 7 days to use the software for free before entering into the premium subscription.
					You will not be charged during the trial period and may cancel at any time. After the 7 days is over,
					you will be automatically billed for the plan you have signed up for.</p>

			</div>
		</div>
	</div>
</template>
<script lang="ts">
export default {
	data() {
		return { current: 'btn1' }
	},
	methods: {
		handleClick(button: string) {
			this.current === button ? this.current = "empty" : this.current = button;
		}
	}
}

</script>