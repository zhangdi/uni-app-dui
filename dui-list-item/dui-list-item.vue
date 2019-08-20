<template>
    <view class="dui-list-item" :class="[{'clickable': isClickable}]" @click="onClick">
        <block v-if="icon">
            <view class="dui-list-item-icon">
                <dui-icon :type="icon" :size="iconSize" :color="iconColor"></dui-icon>
            </view>
        </block>
        <view class="dui-list-item-container">
            <view class="dui-list-item-content">{{title}}</view>
            <view v-if="isShowArrow" class="dui-list-item-arrow">
                <dui-icon type="angle-right" color="#ABABAB" size="56rpx"></dui-icon>
            </view>
        </view>
    </view>
</template>

<script>
    import DuiIcon from '../dui-icon/dui-icon.vue'

    export default {
        components: {
            DuiIcon
        },
        props: {
            title: {
                type: String,
            },
            showArrow: {
                type: [String, Boolean],
                default: false
            },
            clickable: {
                type: [String, Boolean],
                default: true
            },
            icon: String,
            iconSize: {
                type: Number,
                default: 32
            },
            iconColor: {
                type: String,
                default: '#7A7B7C'
            }
        },
        computed: {
            isClickable() {
                return String(this.clickable) == 'true';
            },
            isShowArrow() {
                return String(this.showArrow) == 'true';
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
    @import "../static/scss/vars.scss";
    @import "../static/scss/mixins.scss";

    .dui-list-item {
        display: flex;
        align-items: center;
        font-size: $dui-font-size-base;

        &.clickable:active {
            background-color: rgba(0, 0, 0, .075);
        }

    }

    .dui-list-item-icon {
        display: flex;
        align-items: center;
    }

    .dui-list-item-container {
        min-height: 48px;
        padding: 0 $dui-spacing-row-base;
        flex: 1;
        font-size: $dui-font-size-base;
        display: flex;
        align-items: center;

        @include border-bottom();
    }

    .dui-list-item-content {
        flex: 1;
    }

    .dui-list-item-icon {
        margin-left: $dui-spacing-row-base;
    }

    .dui-list-item-arrow {}
</style>
