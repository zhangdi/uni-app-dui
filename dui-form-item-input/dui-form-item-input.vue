<template>
    <view class="dui-form-item dui-form-item-input">
        <block v-if="label">
            <view class="dui-form-item-input-label">{{label}}</view>
        </block>
        <view class="dui-form-item-input-content">
            <slot></slot>
        </view>
    </view>
</template>

<script>
    export default {
        props: {
            label: {
                type: [Boolean, String],
                default: false
            },

        },
        data() {
            return {};
        },
        methods: {}
    }
</script>

<style lang="scss">
    @import "../static/scss/vars.scss";

    .dui-form-item-input {}

    .dui-form-item-input-label {
        font-size: $dui-font-size-base;
        width: $dui-font-size-base * 6;
    }

    .dui-form-item-input-content {
        margin-left: $dui-spacing-row-base;
        flex: 1;
        display: flex;
        align-items: center;

        input {
            width: 100%;
        }
    }
</style>
