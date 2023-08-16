<script setup lang="ts">
import Header from "@/components/Header/index.vue";
import { RouterView } from "vue-router";
</script>

<template>
	<Header />
	<div class="p-4">
		<RouterView />
	</div>
</template>
