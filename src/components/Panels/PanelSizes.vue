<template>
<div id="sizes">
    <button v-on:mouseup="changeSize('xga')" :class="{active: currentSize === 'xga'}">1024x768</button>
    <button v-on:mouseup="changeSize('wxga')" :class="{active: currentSize === 'wxga'}">1440x900</button>
    <button v-on:mouseup="changeSize('sxga')" :class="{active: currentSize === 'sxga'}">1280x1024</button>
    <button v-on:mouseup="changeSize('ipad-portrait')" :class="{active: currentSize === 'ipad-portrait'}">ipad portrait</button>
</div>

</template>

<script>
export default {
    name: 'PanelSizes',
    data: function () {
        return {
            currentSize: 'xga'
        }
    },
    methods: {
        changeSize: function (size) {
            this.$root.$emit('change_size', size)
            this.currentSize = size;
        }
    }
}
</script>

<style lang="scss" scoped>
#sizes {
    bottom: 0;
    display: flex;
    margin-bottom: 8px;
    justify-content: center;
    position: absolute;
    width: 100%;

    button {
        background: linear-gradient(to bottom, rgba(125,126,125,1) 0%,rgba(14,14,14,1) 100%);
        border: 4px solid rgb(40, 40, 40);
        color: #fff;
        cursor: pointer;
        line-height: 32px;
        margin: 8px;
        width: 128px;

        &.active {
            border: 4px solid gainsboro;
        }
    }
}
</style>