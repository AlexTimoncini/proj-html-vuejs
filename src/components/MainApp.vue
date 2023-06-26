<script>
    import MainCardSectionVue from './MainCardSection.vue';
    import MainNumbersSection from './MainNumbersSection.vue';
    export default {
        name: 'MainApp',
        components: {
            MainCardSectionVue,
            MainNumbersSection
        }
    }
</script>

<template>
    <MainCardSectionVue />
    <MainNumbersSection />
</template>

<style lang="scss">
    
</style>
