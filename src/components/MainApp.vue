<script>
    import MainCardSectionVue from './MainCardSection.vue';
    import MainNumbersSection from './MainNumbersSection.vue';
    import MainGallery from './MainGallery.vue';
    import MainProcess from './MainProcess.vue';
    import MainTeam from './MainTeam.vue'
    import MainClients from './MainClients.vue'
    export default {
        name: 'MainApp',
        components: {
            MainCardSectionVue,
            MainNumbersSection,
            MainGallery,
            MainProcess,
            MainTeam,
            MainClients,
        }
    }
</script>

<template>
    <MainCardSectionVue />
    <MainNumbersSection />
    <MainGallery />
    <MainProcess />
    <MainTeam />
    <MainClients />
</template>

<style lang="scss" scoped>
    
</style>
