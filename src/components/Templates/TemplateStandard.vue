<template>
<div id="template" :class="currentSize">
    <component :is="currentHeader" />

    <div id="content">
        <component :is="currentNav" />

        <main></main>
    </div>

    <component :is="currentFooter" />
</div>
</template>

<script>
import NavStandard from '../Navs/NavStandard.vue'
import NavCompact from '../Navs/NavCompact.vue'
import HeaderStandard from '../Headers/HeaderStandard.vue'
import HeaderProfile from '../Headers/HeaderProfile.vue'
import FooterStandard from '../Footers/FooterStandard.vue'
import FooterFullLinks from '../Footers/FooterFullLinks.vue'

export default {
    name: 'TemplateStandard',
    components: {
        NavStandard,
        NavCompact,
        HeaderStandard,
        HeaderProfile,
        FooterStandard,
        FooterFullLinks
    },
    props: {
        currentSize: String,
        currentNav: String,
        currentHeader: String,
        currentFooter: String
    }
}
</script>

<style lang="scss" scoped>
#template {
    background: #fff;
    box-shadow: 0 10px 28px 0 rgba(0,0,0,0.75);
    bottom: 0;
    display: flex;
    flex-direction: column;
    height: 100vh;
    left: 0;
    margin: auto;
    overflow: auto;
    position: fixed;
    right: 0;
    top: 0;
    transition: 0.25s;
    width: 100vw;

    &.xga {
        height: 768px;
        width: 1024px;
    }
    &.wxga {
        height: 900px;
        width: 1440px;
    }
    &.sxga {
        height: 1024px;
        width: 1280px;
    }
    &.ipad-portrait {
        height: 1024px;
        width: 768px;
    }
}

#content {
    display: flex;
    flex-grow: 1;
}

main {
    border: 1px solid green;
    flex-grow: 1;
}
</style>