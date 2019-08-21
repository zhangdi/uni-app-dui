<template>
	<view class="dui-tag" @click="onClick" :class="['dui-tag-'+type,{'dui-tag-outline':isOutline}]">{{text}}</view>
</template>

<script>
	export default {
		props: {
			text: String,
			type: {
				type: String,
				default: 'primary'
			},
			outline: {
				type: [String, Boolean],
				default: false
			}
		},
		computed: {
			isOutline() {
				return String(this.outline) == 'true';
			}
		},
		data() {
			return {

			};
		},
		methods: {
			onClick(e) {
				this.$emit('click', e);
			}
		}
	}
</script>

<style lang="scss">
	@import '../static/scss/vars.scss';

	@mixin tag ($color) {
		border: 1px solid $color;
		color: #FFFFFF;
		background-color: $color;
		border-radius: 6upx;
		margin-right: $dui-spacing-row-sm;
	}

	@mixin outline-tag ($color) {
		border: 1px solid $color;
		color: $color;
		background-color: transparent;
	}

	.dui-tag {
		display: inline-block;
		padding: $dui-spacing-col-sm/2 $dui-spacing-row-base/2;
		font-size: $dui-font-size-base;
	}

	@each $color,
	$value in $colors {

		.dui-tag-#{$color} {

			@include tag($value);

			&.dui-tag-outline {
				@include outline-tag($value);
			}
		}

	}
</style>
