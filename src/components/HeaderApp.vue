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
        <img src="../assets/shape-bottom.png" alt="wavy white shape">
    </header>
</template>

<style lang="scss" scoped>
    header {
        background-image: url(../assets/banner-bg.png);
        background-repeat: no-repeat;
        background-position: top;
        position: relative;
        width: 100%;
        img{
            position: absolute;
            bottom: 20%;
            height: 80px;
            width: 100%;
        }
    }
</style>
