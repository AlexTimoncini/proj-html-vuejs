<script>
    export default{
        name: 'MainCardSection'
    }
</script>

<template>
    <section id="animationLove">
        <div class="container_size">
            <h2 class="ivy_slogan">Our Love For Animation</h2>
            <h1 class="ivy_title">We're Storytelling Experts With Creative Smarts</h1>
            <p class="ivy_desc">WOur culture inspires the creative and innovative spirit found throughout our Studio. We breathe life into new ideas!</p>
            <div class="ivy_cards">
                <div class="ivy_card">
                    <img src="" alt="">
                    <h3 class="ivy_card_title">3D modeling</h3>
                    <p class="ivy_card_desc">
                        We constantly ask questions. It helps us shape your story and deliver the results you crave. Yep, we'll drill deep to deliver above and beyond your expectations.
                    </p>
                </div>
                <div class="ivy_card">
                    <img src="" alt="">
                    <h3 class="ivy_card_title">Collaboration</h3>
                    <p class="ivy_card_desc">
                        We constantly ask questions. It helps us shape your story and deliver the results you crave. Yep, we'll drill deep to deliver above and beyond your expectations.
                    </p>
                </div>
                <div class="ivy_card">
                    <img src="" alt="">
                    <h3 class="ivy_card_title">Creativity</h3>
                    <p class="ivy_card_desc">
                        We constantly ask questions. It helps us shape your story and deliver the results you crave. Yep, we'll drill deep to deliver above and beyond your expectations.
                    </p>
                </div>
            </div>
        </div>
        <img src="../assets/smart4.png" alt="yellow rocket" class="ivy_rocket">
    </section>
</template>

<style lang="scss" scoped>
    #animationLove{
        position: relative;

        .ivy_rocket{
            position: absolute;
            right: 5px;
            bottom: 5px;
            height: 200px;
            z-index: -1;
        }
    }
</style>
