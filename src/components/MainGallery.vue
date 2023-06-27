<script>
    export default {
        name: 'MainGallery',
        data() {
            return {
                gallery: [
                    '../assets/work1.png',
                    '../assets/work2.png',
                    '../assets/work3.png',
                    '../assets/work4.png',
                ]
            }
        },
        mounted(){
            this.observeTitle();
            this.observeCards();
        },
        methods: {
            getImagePath: function(imgPath) {
                return new URL(imgPath, import.meta.url).href;
            },
            observeTitle(){
                const observer = new IntersectionObserver((entries, observer) =>{
                    entries.filter(e => e.isIntersecting).forEach(entry =>{
                        entry.target.classList.add('slide_from_top');
                        observer.unobserve(entry.target);
                    });
                });
                const titles = document.querySelectorAll('.ivy_small_container')
                titles.forEach(title => observer.observe(title));
            },
            observeCards(){
                const observer = new IntersectionObserver((entries, observer) =>{
                    entries.filter(e => e.isIntersecting).forEach(entry =>{
                        entry.target.classList.add('slide_from_down');
                        observer.unobserve(entry.target);
                    });
                });
                const cards = document.querySelectorAll('.ivy_card')
                cards.forEach(card => observer.observe(card));
            }
        }
    }
</script>

<template>
    <section id="ourWorks">
        <div class="container_size">
            <div class="ivy_small_container">
                <h2 class="ivy_slogan">Our Works</h2>
                <h1 class="ivy_title">Featured Productions</h1>
                <p>Here's just a small sample of some of those projects that we're quite proud of. If you're looking for something specific feel free to get in contact with us.</p>
            </div>
            <div class="ivy_cards">
                <div class="ivy_card" v-for="url,index in gallery">
                    <div class="ivy_wrapper">
                        <img :src="getImagePath(url)" :alt="'work number ' + index">
                        <div class="ivy_hover_wrap">
                            <button class="ivy_playpause">
                                <i class="fa-solid fa-play"></i>
                            </button>
                        </div>
                    </div>
                </div>
            </div>
            <button id="seeMore">See Our Work</button>
        </div>
    </section>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixin' as *;
    #ourWorks{
        padding: 100px 0;
        text-align: center;
        .ivy_small_container{
            @include slide_from_top_start();
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

        .ivy_small_container.slide_from_top{
            @include slide_end();
        }
        .ivy_cards{
            @include flex(row, center, center, wrap);
            padding: 2rem;
            gap: 1rem;
            .ivy_card{
                width: calc((100% / 2) - 0.5rem);
                border: 1px solid $white;
                cursor: pointer;
                position: relative;
                border-radius: 20px;
                overflow: hidden;
                opacity: 0;
                transform: translateY(20px);
                transition: all 1s linear;
                img{
                    width: 100%;
                }
                .ivy_wrapper{
                    overflow: hidden;
                    transition: all 0.3s linear;
                }
                .ivy_hover_wrap{
                    @include flex();
                    background-color: rgb(77, 54, 220, 0.5);
                    width: 100%;
                    height: 100%;
                    position: absolute;
                    top: 0;
                    left: 0;
                    transform: scale(0);
                    transition: all 0.4s linear;
                }

                &:hover .ivy_wrapper{
                    transform: rotateY(-15deg) rotateX(-10deg);
                }

                &:hover .ivy_hover_wrap{
                    transform: scale(1);
                }
                
                .ivy_playpause{
                @include positionCenter;
                background-color: $white;
                border: none;
                height: 70px;
                width: 70px;
                border-radius: 50%;
                text-align: center;
                i{
                    font-size: 1.5rem;
                    color: $orange;
                }
            }
            }
            .ivy_card:nth-child(1){
                transition-delay: 200ms;
            }
            .ivy_card:nth-child(2){
                transition-delay: 400ms;
            }
            .ivy_card:nth-child(3){
                transition-delay: 600ms;
            }
            .ivy_card:nth-child(4){
                transition-delay: 800ms;
            }

            .ivy_card.slide_from_down{
                @include slide_end();
            }

        }

        #seeMore{
            border: 1px solid $pink;
            padding: 0.9rem 2.2rem;
            font-size: 1.2rem;
            color: $purple;
            background: none;
            border-radius: 35px;
            margin-top: 1rem;
            cursor: pointer;
        }
    }
</style>
