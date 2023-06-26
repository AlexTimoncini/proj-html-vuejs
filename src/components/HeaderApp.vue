<script>
    import NavbarHeader from './NavbarHeader.vue';
    import HeaderJumbo from './HeaderJumbo.vue';
    export default {
        name: 'HeaderApp',
        components : {
            NavbarHeader,
            HeaderJumbo
        }
    }
</script>

<template>
    <header>
        <NavbarHeader />
        <HeaderJumbo />
    </header>
</template>

<style lang="scss">
    header {
        background-image: url(../assets/banner-bg.png);
        background-repeat: no-repeat;
        background-position: top;
    }
</style>
