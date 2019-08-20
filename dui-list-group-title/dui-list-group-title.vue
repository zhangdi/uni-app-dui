<template>
    <view class="dui-list-group-title" :style="{'color': color, 'dui-list-group-title-outline':outline}">
        {{title}}
    </view>
</template>

<script>
    export default {
        props: {
            color: {
                type: String,
                default: '#666',
            },
            outline: {
                type: Boolean,
                default: true
            },
            title: {
                type: String,
            }
        },
        data() {
            return {

            };
        }
    }
</script>

<style lang="scss" scoped>
    @import "../static/scss/dui.scss";

    .dui-list-group-title {
        padding: $dui-spacing-col-sm $dui-spacing-row-base;
        font-size: $dui-font-size-base;
        position: relative;
        color: $dui-text-color-secondary;

        &.dui-list-group-title-outline {
            background-color: #FFF;
            color: $dui-text-color-primary;

            &:before {
                position: absolute;
                z-index: 10;
                right: 0;
                top: 0;
                left: 0;
                height: 1px;
                content: '';
                -webkit-transform: scaleY(0.5);
                transform: scaleY(0.5);
                background-color: $dui-border-color;
            }
        }
    }
</style>
