<template>
	<view class="mm_view" v-if="!url">
		<slot></slot>
	</view>
	<view class="mm_view" @click="openBrowser()" v-else-if="url.indexOf('http:') === 0 || url.indexOf('https:') === 0">
		<slot></slot>
	</view>
	<router-link class="mm_view" :to="url" v-else>
		<slot></slot>
	</router-link>
</template>

<script>
	export default {
		props: {
			url: {
				type: String,
				default: ""
			},
			type: {
				type: String,
				default: ""
			}
		},
		methods: {
			openBrowser: function openBrowser() {
				if (window) {
					window.open(this.url);
				}
			}
		}
	};
</script>

<style>
</style>
