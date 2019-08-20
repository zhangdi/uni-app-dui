<template>
    <view class="dui-form-item dui-form-item-textarea">
        <view class="dui-form-item-textarea-label">{{label}}</view>
        <view class="dui-form-item-textarea-content">
            <slot></slot>
        </view>
    </view>
</template>

<script>
    export default {
        props: {
            label: String
        },
        data() {
            return {

            };
        }
    }
</script>

<style lang="scss" scoped>
    @import "../static/scss/vars.scss";
    @import "../static/scss/mixins.scss";

    .dui-form-item-textarea {
        align-items: stretch;
        padding: $dui-spacing-col-base $dui-spacing-row-base;
    }

    .dui-form-item-textarea-label {
        font-size: $dui-font-size-base;
        width: $dui-font-size-base * 6;
        height: 100%;
    }

    .dui-form-item-textarea-content {
        margin-left: $dui-spacing-row-base;
        flex: 1;
    }
    
</style>
