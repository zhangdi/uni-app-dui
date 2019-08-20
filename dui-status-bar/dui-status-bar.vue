<template>
	<view class="dui-status-bar">
		<slot></slot>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			};
		}
	}
</script>

<style lang="scss">
	.dui-status-bar {
		height: 20px;
		height: var(--status-bar-height);
		width: 100%;
	}
</style>
