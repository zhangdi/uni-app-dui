<template>
	<view class="dui-section-title" :class="['dui-section-title-' + type]">
		<view @click="onClick" class="dui-section-title-main">
			{{title}}
		</view>
		<block v-if="isShowMore">
			<view @click="onClickMore" class="dui-section-title-more">
				<slot></slot>
			</view>
		</block>
	</view>
</template>

<script>
	export default {
		props: {
			title: String,
			type: {
				type: String,
				default: "primary"
			},
			showMore: [String, Boolean]

		},
		computed: {
			isShowMore() {
				return String(this.showMore) == 'true';
			}
		},
		data() {
			return {

			};
		},
		methods: {
			onClick(e) {
				this.$emit('click', e);
			},
			onClickMore(e) {
				this.$emit('clickMore', e);
			}
		}
	}
</script>

<style lang="scss">
	@import '../static/scss/vars.scss';

	.dui-section-title {
		display: flex;
		padding: $dui-spacing-col-sm $dui-spacing-row-base;
		background-color: #FFF;
		color: $dui-text-color-primary;
		border-style: solid;
		border-width: 0 0 0 10upx;
		border-color: #007AFF;
		align-items: center;
		font-size: $dui-font-size-lg;
	}

	@each $color,
	$value in $colors {

		.dui-section-title-#{$color} {
			border-color: $value;
		}

	}

	.dui-section-title-main {
		flex: 1;
	}
	
	.dui-section-title-more {
		font-size: $dui-font-size-base;
	}

</style>
