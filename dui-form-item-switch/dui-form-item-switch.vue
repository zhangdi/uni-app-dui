<template>
    <view class="dui-form-item dui-form-item-switch">
        <view class="dui-form-item-switch-label">{{label}}</view>
        <view class="dui-form-item-switch-content">
            
        </view>
        <view class="dui-form-item-switch-control">
            <slot></slot>
        </view>
    </view>
</template>

<script>
    export default {
        props: {
            label: {
                type: String
            }
        },
        data() {
            return {

            };
        }
    }
</script>

<style lang="scss">
    @import "../static/scss/vars.scss";
    @import "../static/scss/mixins.scss";

    .dui-form-item-switch {
        
    }

    .dui-form-item-switch-content {
        flex: 1;
        display: flex;
        align-items: center;
        justify-content: end;
    }
</style>
