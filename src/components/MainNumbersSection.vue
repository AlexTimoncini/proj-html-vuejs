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
        <img src="../assets/shape-top.png" alt="white wavy shape" class="wave wave_top" loading="lazy">
        <div class="container_size">
            <h1 class="ivy_title">Anidio Quick Facts</h1>
            <div class="ivy_cards">
                <div class="ivy_card_counter" v-for="number in anidioNumbers">
                    <h2>{{ number.amount }}</h2>
                    <p>{{ number.name }}</p>
                </div>
            </div>
        </div>
        <!--BACKGROUND IMAGES-->
        <img src="../assets/globe.png" alt="globe img" id="globeRotating" loading="lazy">
        <img src="../assets/shape-bottom.png" alt="white wavy shape" class="wave wave_bot" loading="lazy">
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
            .ivy_title{
            @include slide_from_top_start();
            font-size: 3.5rem;
            margin-bottom: 5rem;
            z-index: 2;
            }
            .ivy_title.slide_from_top{
                @include slide_end();
            }
            .ivy_cards{
                @include flex(row, center, center, wrap);
                flex-grow: 1;
                gap: 2rem;
                .ivy_card_counter{
                    border: 1px solid $darkGrey;
                    width: calc(100% / 4 - 2rem);
                    padding: 3rem 0;
                    border-radius: 20px;
                    cursor: pointer;
                    transition: all 0.1s linear;
                    z-index: 2;
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
            top: 30%;
            height: 50%;
            animation: spin 5s linear infinite;
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

        @media only screen and (max-width: 1200px){

            #counter #globeRotating{
                left: 30%;
            }
            #counter .container_size .ivy_cards .ivy_card_counter{
                width: calc(100% / 3 - 2rem);
                
            }
        }

        @media only screen and (max-width: 992px){
            #counter #globeRotating{
                left: 25%;
            }
            #counter .container_size .ivy_cards .ivy_card_counter{
                width: calc(100% / 2 - 2rem);
            }
        }

        @media only screen and (max-width: 576px){
            #counter #globeRotating{
                left: 0%;
            }
            #counter .container_size .ivy_cards .ivy_card_counter{
                width: calc(100%);
            }
        }
</style>
