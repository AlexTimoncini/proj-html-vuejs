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
        mounted(){
            this.observeTitle();
        },
        methods: {
            observeTitle(){
                const observer = new IntersectionObserver((entries, observer) =>{
                    entries.filter(e => e.isIntersecting).forEach(entry =>{
                        entry.target.classList.add('slide_from_top');
                        observer.unobserve(entry.target);
                    });
                });
                const titles = document.querySelectorAll('h1')
                titles.forEach(title => observer.observe(title)); 
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
        <!--BACKGROUND IMAGES-->
        <img src="../assets/shape-bottom.png" alt="white wavy shape" class="wave wave_bot">
        <img src="../assets/globe.png" alt="globe img" id="globeRotating">
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
        z-index: -2;
        .container_size{
            padding: 100px 0;
            h1{
                opacity: 0;
                transform: translateY(-20px);
                font-size: 3.5rem;
                margin-bottom: 5rem;
                transition: all 1s linear;
                transition-delay: 200ms;
            }
            h1.slide_from_top{
                opacity: 1;
                transform: translateY(0);
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
            display: block;
        }
        .wave_top{
            top: -1px;
        }
        .wave_bot{
            bottom: -1px;
        }
        #globeRotating{
            position: absolute;
            left: 42%;
            top: 10%;
            height: 80%;
            animation: spin 5s linear infinite;
            z-index: -1;
            display: block;
        }

        @keyframes spin {
            0%{
                transform: rotate(0);
            }
            100%{
                transform: rotate(1turn);
            }
        }
    }
</style>
