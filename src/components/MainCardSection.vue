<script>
    export default{
        name: 'MainCardSection'
    }
</script>

<template>
    <section id="animationLove">
        <div class="container_size">

            <div class="ivy_small_container">
                <h2 class="ivy_slogan">Our Love For Animation</h2>
                <h1 class="ivy_title">We're Storytelling Experts With Creative Smarts</h1>
                <p>Our culture inspires the creative and innovative spirit found throughout our Studio. We breathe life into new ideas!</p>
            </div>
            <div class="ivy_cards">
                <div class="ivy_card">
                    <img src="../assets/smart1.png" alt="smart icon">
                    <h3 class="ivy_card_title">3D modeling</h3>
                    <p class="ivy_card_desc">
                        We constantly ask questions. It helps us shape your story and deliver the results you crave. Yep, we'll drill deep to deliver above and beyond your expectations.
                    </p>
                </div>
                <div class="ivy_card">
                    <img src="../assets/smart2.png" alt="smart icon">
                    <h3 class="ivy_card_title">Collaboration</h3>
                    <p class="ivy_card_desc">
                        We constantly ask questions. It helps us shape your story and deliver the results you crave. Yep, we'll drill deep to deliver above and beyond your expectations.
                    </p>
                </div>
                <div class="ivy_card">
                    <img src="../assets/smart3.png" alt="smart icon">
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
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixin' as *;

    #animationLove{
        position: relative;
        text-align: center;
        padding: 100px 0;
        color: $purple;

        .ivy_small_container{
            width: 60%;
            margin: 0 auto;
            .ivy_slogan{
                color: $blue;
                padding-bottom: 1.5rem;
            }
            .ivy_title{
                font-size: 3.5rem;
                padding-bottom: 1rem;
            }
        }

        .ivy_cards{
            @include flex(row, center, center, wrap);
            gap: 2rem;
            width: 80%;
            margin: 3rem 0 5rem auto;

            .ivy_card{
                width: calc(100% / 3 - 2rem);
                padding: 2.5rem 1rem;
                background-color: antiquewhite;
                border-radius: 35px;
                border: 1px solid rgb(178,181,210);

                .ivy_card_title{
                    font-size: 1.8rem;
                    margin: 1rem 0;
                }

                .ivy_card_desc{
                    font-size: 1.1rem;
                }
            }
        }
        .ivy_rocket{
            position: absolute;
            right: 5px;
            bottom: 5px;
            height: 200px;
            z-index: -1;
        }
    }
</style>
