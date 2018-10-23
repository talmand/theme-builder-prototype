<template>
<div id="panels">
    <div id="steps">
        <button v-on:mouseup="changeStep('templates')" :class="{active: currentStep === 'templates'}">templates</button>
        <button v-on:mouseup="changeStep('regions')" :class="{active: currentStep === 'regions'}">regions</button>
        <button v-on:mouseup="changeStep('components')" :class="{active: currentStep === 'components'}">components</button>
        <button>themes</button>
    </div>

    <transition>
    <div class="step_1" v-show="currentStep === 'templates'">
        <button v-on:mouseup="$root.$emit('change_template', 'TemplateStandard')" :class="{active: currentTemplate === 'TemplateStandard'}">standard</button>
        <button v-on:mouseup="$root.$emit('change_template', 'TemplateLeftNav')" :class="{active: currentTemplate === 'TemplateLeftNav'}">left nav</button>
    </div>
    </transition>

    <transition>
    <div class="step_1" v-show=" currentStep === 'regions'">
        <button v-on:mouseup="changeRegion('navs')" :class="{active: currentRegion === 'navs'}">navs</button>
        <button v-on:mouseup="changeRegion('headers')" :class="{active: currentRegion === 'headers'}">headers</button>
        <button v-on:mouseup="changeRegion('footers')" :class="{active: currentRegion === 'footers'}">footers</button>
    </div>
    </transition>
    <transition>
    <div class="step_2" v-show="currentRegion === 'navs'">
        <button v-on:mouseup="$root.$emit('change_nav', 'NavStandard')" :class="{active: currentNav === 'NavStandard'}">standard</button>
        <button v-on:mouseup="$root.$emit('change_nav', 'NavCompact')" :class="{active: currentNav === 'NavCompact'}">compact</button>
    </div>
    </transition>
    <transition>
    <div class="step_2" v-show="currentRegion === 'headers'">
        <button v-on:mouseup="$root.$emit('change_header', 'HeaderStandard')" :class="{active: currentHeader === 'HeaderStandard'}">standard</button>
        <button v-on:mouseup="$root.$emit('change_header', 'HeaderProfile')" :class="{active: currentHeader === 'HeaderProfile'}">profile only</button>
    </div>
    </transition>
    <transition>
    <div class="step_2" v-show="currentRegion === 'footers'">
        <button v-on:mouseup="$root.$emit('change_footer', 'FooterStandard')" :class="{active: currentFooter === 'FooterStandard'}">standard</button>
        <button v-on:mouseup="$root.$emit('change_footer', 'FooterFullLinks')" :class="{active: currentFooter === 'FooterFullLinks'}">full links</button>
    </div>
    </transition>

    <transition>
    <div class="step_1" v-show="currentStep === 'components'">
        <button v-on:mouseup="changeComponent('navs')" :class="{active: currentComponent === 'navs'}">navs</button>
        <button>headers</button>
        <button>footers</button>
    </div>
    </transition>
    <transition>
    <div class="step_2" v-show="currentComponent === 'navs'">
        <button v-on:mouseup="$root.$emit('change_nav_component', 'ComponentNavStandard')" :class="{active: currentNav === 'ComponentNavStandard'}">standard</button>
        <button v-on:mouseup="$root.$emit('change_nav_component', 'ComponentNavCompact')" :class="{active: currentNav === 'ComponentNavStandard'}">compact</button>
    </div>
    </transition>
</div>
</template>

<script>
export default {
    name: 'PanelSteps',
    props: {
        currentTemplate: String,
        currentNav: String,
        currentHeader: String,
        currentFooter: String
    },
    data: function () {
        return {
            currentStep: null,
            currentRegion: null,
            currentComponent: null
        }
    },
    methods: {
        changeStep: function (step) {
            this.currentStep = step;
            this.currentRegion = null;
            this.currentComponent = null;
        },
        changeRegion: function (region) {
            this.currentRegion = region;
        },
        changeComponent: function (component) {
            this.currentComponent = component;
        }
    }
}
</script>

<style lang="scss" scoped>
#panels {
    align-items: center;
    display: flex;
    flex-direction: column;
    position: absolute;
    top: 0;
    width: 100%;

    .step_1 {
        position: absolute;
        text-align: center;
        top: 50px;
        will-change: opacity, top;
        z-index: 5;
    }
    .step_2 {
        position: absolute;
        text-align: center;
        top: 100px;
        will-change: opacity, top;
    }

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

    .v-enter {
        opacity: 0;
        top: 0;
    }
    .v-enter-active {
        transition: 0.5s;
    }
    .v-enter-to {
        opacity: 1;
    }
    .v-leave {
        opacity: 1;
    }
    .v-leave-active {
        transition: 0.5s;
    }
    .v-leave-to {
        opacity: 0;
        top: 100px;
    }
}
#steps {
    z-index: 10;
}
</style>