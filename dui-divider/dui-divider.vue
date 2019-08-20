<template>
    <view class="dui-divider" :style="{color: color}">
        <text>{{text}}</text>
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
        padding: $dui-spacing-col-base 0;
        text-align: center;
        display: flex;
        align-items: center;

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
