<template>
    <view class="dui-list-item" :class="[{'clickable': true}]" @click="onClick">
        <view></view>
        <view class="dui-list-item-content">{{title}}</view>
        <view v-if="showArrow" class="dui-list-item-arrow">
            <dui-icon type="angle-right" color="#ABABAB" size="56rpx"></dui-icon>
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
                type: Boolean,
                default: false
            },
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
        min-height: 48px;
        
        @include border-bottom();

        &.clickable:active {
            background-color: rgba(0, 0, 0, .075);
        }

    }

    .dui-list-item-content {
        padding: 0 $dui-spacing-row-base;
        flex: 1;
        font-size: $dui-font-size-base;
    }

    .dui-list-item-arrow {
        margin-left: $dui-spacing-row-base;
        margin-right: $dui-spacing-row-base;
    }
</style>
