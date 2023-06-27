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
        <!-- Background Images -->
        <img src="../assets/banner-bg.png" alt="background color purple" id="bgGradient">
        <img src="../assets/shape-bottom.png" alt="wavy white shape" id="whiteWave">
        <img src="../assets/left-man.png" alt="spaceman img" id="leftSpaceMan">
        <img src="../assets/right-man.png" alt="spaceman img" id="rightSpaceMan">
        <img src="../assets/dots-left.png" alt="stars img" id="leftStars">
        <img src="../assets/dots-right.png" alt="stars img" id="rightStars">
        <img src="../assets/globe1.png" alt="globe cartoon img" id="globeLeft">
        <img src="../assets/globe2.png" alt="globe cartoon img" id="globeRight">
        <img src="../assets/globe3.png" alt="globe cartoon img" id="globeTop">
        <img src="../assets/light.png" alt="ufo spaceship img" id="ufo">
    </header>
</template>

<style lang="scss" scoped>
    header {
        position: relative;

        img{
            position: absolute;
            display: block;
        }
        /**BACKGROUND IMAGES BEHAVIOUR**/
        #bgGradient{
            width: 100%;
            top: 0;
            left: 0;
            height: 900px;
            z-index: -10;
        }
        #whiteWave{
            top: 820px;
            height: 80px;
            width: 100%;
        }
        #leftSpaceMan{
            top: 300px;
            left: 100px;
            animation: floatUpDown 4s linear infinite;
        }
        #rightSpaceMan{
            top: 300px;
            right: 100px;
            animation: floatUpDown 4s linear infinite;
        }
        #leftStars{
            top: 100px;
            left: 50px;
            z-index: -1;
        }
        #rightStars{
            top: 100px;
            right: 50px;
            z-index: -5;

        }
        #globeLeft{
            top: 130px;
            left: 160px;
            width: 120px;
            z-index: -5;
            animation: spin 4s linear infinite;

        }
        #globeRight{
            top: 130px;
            right: 600px;
            width: 100px;
            z-index: -5;
            animation: spin 4s linear infinite;

        }
        #globeTop{
            top: 0;
            transform: translateY(-50%);
            left: 30%;
            width: 300px;
            z-index: -5;
        }
        #ufo{
            top: 100px;
            right: 300px;
            animation: shake 2s linear infinite;
        }
        @keyframes floatUpDown {
            0%
            {
                transform: translateY(0);
            }
            25%
            {
                transform: translateY(-10px);
            }
            50%
            {
                transform: translateY(0);
            }
            75%
            {
                transform: translateY(10px);
            }
            100%
            {
                transform: translateY(0);
            }
        }
        @keyframes spin {
            0%
            {
                transform: rotate(0);
            }
            100%
            {
                transform: rotate(1turn);
            }
        }
        @keyframes shake {
            0%
            {
                transform: rotate(0);
            }
            25%
            {
                transform: rotate(-5deg);
            }
            50%
            {
                transform: rotate(0);
            }
            75%
            {
                transform: rotate(5deg);
            }
            100%
            {
                transform: rotate(0);
            }

        }
    }
</style>
