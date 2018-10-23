<template>
    <div id="app">
        <PanelSteps 
            :currentTemplate="currentTemplate"
            :currentNav="currentNav"
            :currentHeader="currentHeader"
            :currentFooter="currentFooter"
        />
        <PanelSizes />
        <component
            :is="currentTemplate"
            :currentSize="currentSize"
            :currentNav="currentNav"
            :currentHeader="currentHeader"
            :currentFooter="currentFooter"
        />
    </div>
</template>

<script>
import PanelSteps from './components/Panels/PanelSteps.vue'
import PanelSizes from './components/Panels/PanelSizes.vue'
import TemplateStandard from './components/Templates/TemplateStandard.vue'
import TemplateLeftNav from './components/Templates/TemplateLeftNav.vue'

export default {
    name: 'app',
        components: {
        PanelSizes,
        PanelSteps,
        TemplateStandard,
        TemplateLeftNav
    },
    data: function () {
        return {
            currentSize: 'xga',
            currentTemplate: 'TemplateStandard',
            currentNav: 'NavStandard',
            currentHeader: 'HeaderStandard',
            currentFooter: 'FooterStandard'
        }
    },
    created: function () {
        this.$root.$on('change_size', size => this.currentSize = size);
        this.$root.$on('change_template', template => this.currentTemplate = template);
        this.$root.$on('change_nav', nav => this.currentNav = nav);
        this.$root.$on('change_header', header => this.currentHeader = header);
        this.$root.$on('change_footer', footer => this.currentFooter = footer);
    }
}
</script>

<style>
html {
    box-sizing: border-box;
}
*, *:before, *:after {
    box-sizing: inherit;
}

html,
body {
    height: 100%;
    margin: 0;
    padding: 0;
}
body {
    background: radial-gradient(ellipse at center, rgba(14,14,14,1) 0%,rgba(125,126,125,1) 100%);
    font-size: 10px;
}
</style>
