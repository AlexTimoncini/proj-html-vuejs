<script>
    import MainCardSectionVue from './MainCardSection.vue';
    import MainNumbersSection from './MainNumbersSection.vue';
    import MainGallery from './MainGallery.vue';
    export default {
        name: 'MainApp',
        components: {
            MainCardSectionVue,
            MainNumbersSection,
            MainGallery
        }
    }
</script>

<template>
    <MainCardSectionVue />
    <MainNumbersSection />
    <MainGallery />
</template>

<style lang="scss" scoped>
    
</style>
