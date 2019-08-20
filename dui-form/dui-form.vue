<template>
    <view class="dui-form">
        <slot></slot>
    </view>
</template>

<script>
    export default {
        data() {
            return {

            };
        },
    }
</script>

<style lang="scss" scoped>
    @import "../static/scss/vars.scss";
    @import "../static/scss/mixins.scss";

    .dui-form {
        background-color: $dui-bg-color-white;

        @include border-y();
    }
</style>
