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
        <div class="container_size">
            <h1>Anidio Quick Facts</h1>
            <div class="ivy_cards">
                <div class="ivy_card" v-for="number in anidioNumbers">
                    <h2>{{ number.amount }}</h2>
                    <p>{{ number.name }}</p>
                </div>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixin' as *;
    #counter{
        background-image: url(../assets/counter-bg.png);
        background-size: cover;
        color: $white;
        padding: 100px 0;
        text-align: center;

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

                h2{
                    font-size: 3rem;
                }

                p{
                    font-size: 1.1rem;
                    color: $orange;
                }
            }
        }
    }
</style>
