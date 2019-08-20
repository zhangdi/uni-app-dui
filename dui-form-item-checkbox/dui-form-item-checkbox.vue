<template>
	<view class="dui-form-item dui-form-item-checkbox">
		<view class="dui-form-item-checkbox-content">
			<slot></slot>
		</view>
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
	@import "../static/scss/vars.scss";
	@import "../static/scss/mixins.scss";

	.dui-form-item-checkbox {
	}

	.dui-form-item-checkbox-content {
		flex: 1;
		align-items: center;
	}

	.dui-form .dui-form-item-checkbox:last-child {
		&:after {
			height: 0px;
		}
	}
</style>
