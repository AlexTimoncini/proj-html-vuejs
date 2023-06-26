<script>
    import MainCardSectionVue from './MainCardSection.vue';
    import MainNumbersSection from './MainNumbersSection.vue';
    import MainGallery from './MainGallery.vue';
    import MainProcess from './MainProcess.vue';
    import MainTeam from './MainTeam.vue'
    export default {
        name: 'MainApp',
        components: {
            MainCardSectionVue,
            MainNumbersSection,
            MainGallery,
            MainProcess,
            MainTeam
        }
    }
</script>

<template>
    <MainCardSectionVue />
    <MainNumbersSection />
    <MainGallery />
    <MainProcess />
    <MainTeam />
</template>

<style lang="scss" scoped>
    
</style>
