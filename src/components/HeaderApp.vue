<script>
    import NavbarHeader from './NavbarHeader.vue';
    export default {
        name: 'HeaderApp',
        components : {
            NavbarHeader
        }
    }
</script>

<template>
    <header>
        <NavbarHeader />
    </header>
</template>

<style lang="scss">
    header {
        background-image: url(../assets/banner-bg.png);
        background-repeat: no-repeat;
        background-position: top;
    }
</style>
