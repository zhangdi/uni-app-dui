<template>
    <view class="dui-media-list-item" :class="[{'clickable': isClickable}]" @click="onClick">
        <block v-if="imageUrl">
            <view class="dui-media-list-item-media">
                <image :src="imageUrl" :style="{width: imageWidth,height: imageHeight}"></image>
            </view>
        </block>
        <view class="dui-media-list-item-body">
            <block v-if="title">
                <view class="dui-media-list-item-title">{{title}}</view>
            </block>
            <block v-if="desc">
                <view class="dui-media-list-item-desc">{{desc}}</view>
            </block>
        </view>
    </view>
</template>

<script>
    export default {
        props: {
            // 图片地址
            imageUrl: {
                type: String,
            },
            imageSize: {
                type: [String, Number],
                default: 180
            },
            clickable: {
                type: [String, Boolean],
                default: true
            },
            icon: String,
            title: String,
            desc: String
        },
        computed: {
            imageWidth() {
                if (typeof(this.imageSize) == 'number') {
                    return this.imageSize + 'rpx';
                }
                return this.imageSize;
            },
            imageHeight() {
                if (typeof(this.imageSize) == 'number') {
                    return this.imageSize + 'rpx';
                }
                return this.imageSize;
            },
            isClickable() {
                return String(this.clickable) == 'true';
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
        }
    }
</script>

<style lang="scss" scoped>
    @import '../static/scss/vars.scss';
    @import "../static/scss/mixins.scss";

    .dui-media-list-item {
        display: flex;
        font-size: $dui-font-size-base;
        min-height: 48px;
        padding: $dui-spacing-col-base $dui-spacing-row-base;

        @include border-bottom();

        &.clickable:active {
            background-color: rgba(0, 0, 0, .075);
        }
    }

    .dui-media-list-item-media {
        margin-right: $dui-spacing-row-base;
        
        image {
            border-radius: 14rpx;
        }
    }

    .dui-media-list-item-body {
        flex: 1;
    }

    .dui-media-list-item-title {
        color: $dui-text-color-primary;
        font-size: $dui-font-size-lg;
        margin-bottom: $dui-spacing-col-sm;
    }

    .dui-media-list-item-desc {
        color: $dui-text-color-hint;
        font-size: $dui-font-size-base;
    }
</style>
