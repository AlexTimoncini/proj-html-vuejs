<script>
    export default{
        name: 'AppLoader'
    }
</script>

<template>
    <div class="wrapper">
        <div class="img_box">
            <img src="../assets/rocket-banner.png" alt="">
        </div>
    </div>
</template>

<style lang="scss" scoped>
    .wrapper{
        background: url(../assets/preloader.png);
        display: flex;
        background-size: cover;
        height: 100vh;
        width: 100%;
        position: absolute;
        top: 0;
        .img_box{
            margin: auto;
            animation: slide 3s linear infinite;
            img{
                display: block;
            }
            @keyframes slide {
                0%{
                    transform: translateX(-100px);
                }
                50%{
                    transform: translateX(100px);
                    
                }
                100%{
                    transform: translateX(-100px);
                }
            }
        }
    }
</style>
