<template>
	<view class="dui-nav-bar" :class="[{'dui-nav-bar-fixed': isFixed}]">
		<dui-status-bar></dui-status-bar>
		<view class="dui-nav-bar-content">
			<block v-if="isShowBackButton">
				<view class="dui-nav-bar-back" @click="onClickBackButton">
					<dui-icon type="angle-left" :color="backButtonColor" :size="buttonSize"></dui-icon>
				</view>
			</block>
			<block v-if="isShowHomeButton">
				<view class="dui-nav-bar-home" @click="onClickHomeButton">
					<dui-icon type="home" :color="homeButtonColor" :size="buttonSize"></dui-icon>
				</view>
			</block>
			<view class="dui-nav-bar-title">{{title}}</view>
		</view>
	</view>
</template>

<script>
	import DuiStatusBar from '../dui-status-bar/dui-status-bar.vue'
	import DuiIcon from '../dui-icon/dui-icon.vue'
	export default {
		components: {
			DuiStatusBar,
			DuiIcon
		},
		props: {
			title: String,
			fixed: [String, Boolean],
			/**
			 * 是否显示返回按钮
			 */
			showBackButton: {
				type: [String, Boolean],
				default: true,
			},
			backButtonColor: {
				type: String,
				default: '#444'
			},
			showHomeButton: {
				type: [String, Boolean],
				default: true,
			},
			homeButtonColor: {
				type: String,
				default: '#444'
			},
			onClickHome: {
				type: Function,
				default: null
			}
		},
		computed: {
			isFixed() {
				return String(this.fixed) == 'true';
			},
			isShowBackButton() {
				return String(this.showBackButton) == 'true';
			},
			isShowHomeButton() {
				return String(this.showBackButton) == 'true';
			}
		},
		data() {
			return {
				buttonSize: 44,
			};
		},
		methods: {
			onClickBackButton() {
				uni.navigateBack();
			},
			onClickHomeButton() {
				if (this.onClickHome == null) {
					uni.navigateBack({
						delta: 20
					})
				} else {
					this.onClickHome();
				}

			}
		}
	}
</script>

<style lang="scss" scoped>
	@import "../static/scss/dui.scss";

	.dui-nav-bar {
		background-color: #FFFFFF;
		width: 100%;
	}

	.dui-nav-bar-fixed {
		position: fixed;
		z-index: 999;
		top: 0;

	}
	
	.dui-nav-bar-title {
		font-size: $dui-font-size-lg;
	}

	.dui-nav-bar-content {
		height: 44px;
		display: flex;
		align-items: center;
		padding-left: $dui-spacing-row-base;
	}

	.dui-nav-bar-back {
		margin-right: $dui-spacing-row-base;
	}

	.dui-nav-bar-home {
		margin-right: $dui-spacing-row-base;
	}
</style>
