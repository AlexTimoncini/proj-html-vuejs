<script>
    import MainCardSectionVue from './MainCardSection.vue';
    import MainNumbersSection from './MainNumbersSection.vue';
    import MainGallery from './MainGallery.vue';
    import MainProcess from './MainProcess.vue';
    export default {
        name: 'MainApp',
        components: {
            MainCardSectionVue,
            MainNumbersSection,
            MainGallery,
            MainProcess
        }
    }
</script>

<template>
    <MainCardSectionVue />
    <MainNumbersSection />
    <MainGallery />
    <MainProcess />
</template>

<style lang="scss" scoped>
    
</style>
