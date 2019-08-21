<template>
	<view class="dui-divider" :class="{'dui-divider-both':text.length > 0}" :style="{color: color, 'postion': stylePosition}">
		<block v-if="text">
			<text>{{text}}</text>
		</block>
	</view>
</template>

<script>
	export default {
		props: {
			text: String,
			color: {
				type: String,
				default: '#666'
			}
		},
		computed: {
			stylePosition() {
				console.log(this.text.length)
				if (this.text.length == 0) {
					return 'static';
				} else {
					return 'relative';
				}
			}
		},
		data() {
			return {

			};
		}
	}
</script>

<style lang="scss" scoped>
	@import "../static/scss/vars.scss";

	.dui-divider {
		position: relative;
		margin: $dui-spacing-col-base 0;
		text-align: center;
		display: flex;
		align-items: center;

		background-color: $dui-border-color;
		height: 1px;
		-webkit-transform: scaleY(0.5);
		transform: scaleY(0.5);
	}

	.dui-divider-both {
		height: auto;
		background: transparent;
		-webkit-transform: none;
		transform: none;

		&:before {
			content: '';
			flex: 1;
			background-color: $dui-border-color;
			height: 1px;
			-webkit-transform: scaleY(0.5);
			transform: scaleY(0.5);
			margin-right: $dui-spacing-row-base;
		}

		&:after {
			content: '';
			flex: 1;
			background-color: $dui-border-color;
			height: 1px;
			-webkit-transform: scaleY(0.5);
			transform: scaleY(0.5);
			margin-left: $dui-spacing-row-base;
		}
	}
</style>
