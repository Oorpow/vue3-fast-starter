<script setup lang="ts">
import DropDown from "./cpns/Dropdown.vue";
import Card from "@/components/Card/index.vue";

import {
	IconSearch,
	IconUserOutline,
	IconWeatherSunny,
	IconWeatherNight,
} from "@iconify-prerendered/vue-mdi";

const navList = [
	{
		id: 1,
		path: "",
		name: "Home",
	},
	{
		id: 2,
		path: "",
		name: "Shop",
	},
	{
		id: 3,
		path: "",
		name: "About",
	},
	{
		id: 4,
		path: "",
		name: "Contact",
	},
];
</script>

<template>
	<div class="relative">
		<div class="flex w-[90%] h-[80px] items-center mx-auto">
			<div class="w-[150px]">LOGO</div>
			<div class="flex flex-1 justify-center">
				<ul class="flex gap-12">
					<li class="nav-item" v-for="nav in navList" :key="nav.id">
						<span class="item-span__title font-bold">{{ nav.name }}</span>
					</li>
				</ul>
			</div>
			<div class="flex justify-end gap-3">
				<IconSearch class="text-2xl" />
				<IconUserOutline class="text-2xl" />
				<IconWeatherSunny class="text-2xl" />
			</div>
		</div>
		<!-- 隐藏的下拉框 -->
		<DropDown>
			<template #content>
				<div class="w-[90%] mx-auto">
					<div class="flex-1 flex justify-center gap-4 flex-wrap flex-grow-0">
						<template v-for="item in 8" :key="item">
							<Card />
						</template>
					</div>
					<div class="flex justify-center mt-[40px]">
						<span class=" text-white rounded p-4 bg-zinc-900">Explore all demos</span>
					</div>
				</div>
			</template>
		</DropDown>
	</div>
</template>

<style lang="scss" scoped>
.nav-item {
	position: relative;
	&:hover {
		.item-span__title {
			&::after {
				transform-origin: 0% 50%;
				transform: scale3d(1, 1, 1);
			}
		}
	}
}
.item-span__title {
	&::after {
		content: "";
		display: flex;
		width: 100%;
		height: 2px;
		position: relative;
		bottom: -3px;
		transition: transform 0.3s;
		background-color: rgba($color: #000000, $alpha: 0.7);
		transform-origin: 100% 50%;
		transform: scale3d(0, 1, 1);
	}
}
</style>
