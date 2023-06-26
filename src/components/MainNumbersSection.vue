<script>
    export default {
        name: 'MainNumbersSection',
        data() {
            return {
                anidioNumbers: [
                    {
                        name: 'Projects done',
                        amount: '700+'
                    },
                    {
                        name: 'Happy Clients',
                        amount: '250+'
                    },
                    {
                        name: 'Team Members',
                        amount: '25+'
                    },
                    {
                        name: 'Years on the market',
                        amount: '12+'
                    },
                ],
            }
        },
    }
</script>

<template>
    <section id="counter">
        <img src="../assets/shape-top.png" alt="white wavy shape" class="wave wave_top">
        <div class="container_size">
            <h1>Anidio Quick Facts</h1>
            <div class="ivy_cards">
                <div class="ivy_card" v-for="number in anidioNumbers">
                    <h2>{{ number.amount }}</h2>
                    <p>{{ number.name }}</p>
                </div>
            </div>
        </div>
        <img src="../assets/shape-bottom.png" alt="white wavy shape" class="wave wave_bot">
    </section>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixin' as *;
    #counter{
        background-image: url(../assets/counter-bg.png);
        background-size: cover;
        color: $white;
        text-align: center;
        position: relative;

        .container_size{
            padding: 100px 0;
            h1{
                font-size: 3.5rem;
                margin-bottom: 5rem;
            }

            .ivy_cards{
                @include flex();
                column-gap: 2rem;

                .ivy_card{
                    border: 1px solid $darkGrey;
                    width: calc(100% / 4);
                    flex-shrink: 1;
                    padding: 3rem 0;
                    border-radius: 20px;
                    cursor: pointer;
                    transition: all 0.1s linear;
                    h2{
                        font-size: 3rem;
                    }

                    p{
                        font-size: 1.1rem;
                        color: $orange;
                    }

                    &:hover{
                        transform: rotateY(20deg) rotateX(-20deg);
                    }
                }
            }
        }
        .wave{
            position: absolute;
            width: 100%;
            left: 0;
        }
        .wave_top{
            top: 0;
        }
        .wave_bot{
            bottom: 0;
        }
        
    }
</style>
