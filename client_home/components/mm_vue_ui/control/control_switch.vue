<template>
	<div class="control_switch">
		<div class="title" v-if="title" v-html="title"></div>
		<div class="value" v-bind:class="{'disabled': disabled }"><label :class="{ 'active': value === 1 }" @click="set">
				<div class="onoff"><span class="on" v-if="display === '1'"></span><span class="off" v-if="display === '1'"></span></div>
			</label></div>
		<div class="tip" v-if="tip">{{ tip }}</div>
	</div>
</template>

<script>
	import mixin from "@/mixins/control.js";
	export default {
		mixins: [mixin],
		methods: {
			set: function set() {
				var val = 0;

				if (this.value === 0) {
					val = 1;
				}

				this.$emit("input", val);
			}
		}
	};
</script>

<style>
</style>
