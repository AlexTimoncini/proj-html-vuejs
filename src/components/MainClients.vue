<script>
    import 'vue3-carousel/dist/carousel.css'
    import { Carousel, Slide } from 'vue3-carousel';
    import { ref } from 'vue';
    const myCarousel = ref(null);
    export default {
        name: 'MainClients',
        components: {
            Carousel,
            Slide,
        },
        data() {
            return {
                clientList: [
                    {
                        name: '',
                        logo: '../assets/sponsor1.png'
                    },
                    {
                        name: '',
                        logo: '../assets/sponsor2.png'
                    },
                    {
                        name: '',
                        logo: '../assets/sponsor3.png'
                    },
                    {
                        name: '',
                        logo: '../assets/sponsor4.png'
                    },
                    {
                        name: '',
                        logo: '../assets/sponsor5.png'
                    },
                    {
                        name: '',
                        logo: '../assets/sponsor6.png'
                    },
                ],
                breakpoints: {
                    767: {
                        itemsToShow: 3,
                    },
                    992: {
                        itemsToShow: 4,
                    },
                    1200: {
                        itemsToShow: 5,
                    },
                    1400: {
                        itemsToShow: 6,
                    }
                }
            }
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
        },
        mounted() {
            this.observeTitle();
        },
    }
</script>

<template>
    <section id="ourClients">
        <div class="container_size">
            <div class="ivy_small_container">
                <h2 class="ivy_slogan">Why Anidio studio?</h2>
                <h1 class="ivy_title">We Love Our Clients</h1>
                <p>We are trusted throughout adland and have a wealth of recommendations from start-ups to renowned global brands.</p>
            </div>
            <Carousel
            :items-to-show="2" 
            :breakpoints="breakpoints"
            :wrap-around="true" 
            :autoplay="2000" 
            :pauseAutoplayOnHover="true" 
            :snapAlign="'start'">
                <Slide v-for="client in clientList" :key="client">
                    <div class="carousel__item">
                        <div class="ivy_icon_box">
                            <img :src="getImagePath(client.logo)" :alt="client.name" loading="lazy">
                        </div>
                    </div>
                </Slide>
            </Carousel>
        </div>
    </section>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixin' as *;
    #ourClients{
        padding: 100px 0;
        .ivy_small_container{
            width: 60%;
            margin: 0 auto;
            text-align: center;
            padding-bottom: 3rem;
            @include slide_from_top_start();

            .ivy_slogan{
                color: $blue;
                padding-bottom: 1.5rem;
            }
            .ivy_title{
                font-size: 3.5rem;
                padding-bottom: 1rem;
            }
        }
        .carousel__item{
            flex-grow: 1;
            img{
                display: block;
                width: 100%;
            }
        }
        .carousel__slide {
            padding: 10px;
        }
        .carousel__prev,
        .carousel__next {
            box-sizing: content-box;
            border: 5px solid transparent;
        }

        .ivy_small_container.slide_from_top{
            @include slide_end();
        }
    }
    @media only screen and (max-width: 992px) {
        #ourClients .ivy_small_container{
            width: 100%;
        }
    }
</style>
