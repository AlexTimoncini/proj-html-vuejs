<script>
    import 'vue3-carousel/dist/carousel.css'
    import { Carousel, Slide } from 'vue3-carousel';
    import { ref } from 'vue';
    const processCarousel = ref(null);
    export default {
        name: 'MainProcess',
        components: {
            Carousel,
            Slide,
        },
        data() {
            return {
                processList: [
                    {
                        name: 'Scripting',
                        description: "We'll take your idea and create a technical script which consists of action notes and animation descriptions",
                        img: '../assets/process1.png'
                    },
                    {
                        name: 'Pre-Production',
                        description: "We'll take your idea and create a technical script which consists of action notes and animation descriptions",
                        img: '../assets/process2.png'
                    },
                    {
                        name: 'Scripting',
                        description: "We'll take your idea and create a technical script which consists of action notes and animation descriptions",
                        img: '../assets/process1.png'
                    },
                    {
                        name: 'Pre-Production',
                        description: "We'll take your idea and create a technical script which consists of action notes and animation descriptions",
                        img: '../assets/process2.png'
                    },
                ],
                breakpoints: {
                    767: {
                        itemsToShow: 2,
                        snapAlign: 'start',
                    }
                }
            }
        },
        mounted() {
            this.processCarousel = this.$refs.processCarousel;
            this.observeTitle();
        },
        methods: {
            prev(){
                this.processCarousel.prev()
            },
            next(){
                this.processCarousel.next()
            },
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
                const titles = document.querySelectorAll('.ivy_heading')
                titles.forEach(title => observer.observe(title));
            },
        }
    }
</script>

<template>
    <section id="ourProcess">
        <div class="container_size">
            <div class="ivy_left_side">
                <img src="../assets/process-thumb.png" alt="user riding a rocket" loading="lazy">
            </div>
            <div class="ivy_right_side">
                <div class="ivy_small_container">
                    <div class="ivy_heading">
                        <h2 class="ivy_slogan">Our Process</h2>
                        <h1 class="ivy_title">Our Process for Your Animation Production</h1>
                        <p class="ivy_desc">We have an effective process for working on animation</p>
                    </div>
                    <Carousel
                    ref="processCarousel"
                    :breakpoints="breakpoints"
                    :items-to-show="1" 
                    :wrap-around="true" 
                    :autoplay="2000" 
                    :pauseAutoplayOnHover="true" 
                    :snapAlign="'center'">
                        <Slide v-for="slide, index in processList" :key="slide">
                            <div class="carousel__item">
                                <div class="ivy_icon_box">
                                    <img :src="getImagePath(slide.img)" :alt="slide.name" loading="lazy">
                                </div>
                                <h1>{{ slide.name }}</h1>
                                <p>{{ slide.description }}</p>
                                <div class="ivy_index_banner">
                                    {{ index + 1 }}
                                </div>
                            </div>
                        </Slide>
                    </Carousel>
                    <div class="ivy_carousel_nav">
                        <button @click="prev">
                            <i class="fa-solid fa-arrow-left"></i>
                        </button>
                        <button @click="next">
                            <i class="fa-solid fa-arrow-right"></i>
                        </button>
                    </div>
                </div>
            </div>
            <!--BACKGROUND IMAGES-->
            <img src="../assets/smart4.png" alt="yellow rocket" class="ivy_rocket" loading="lazy"> 

        </div>
    </section>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixin' as *;
    #ourProcess{
        padding: 100px 0 200px;
        position: relative;
        .container_size{
            display: flex;
            .ivy_left_side{
                width: 50%;
                position: relative;
                img{
                    position: absolute;
                    left: 0;
                    top: 0;
                    transform: translateX(-50%);
                    transition: all 0.2s linear;
                    display: block;

                    &:hover{
                        transform: translateX(-47%);
                    }
                }
            }
            .ivy_right_side{
                width: 50%;
                .ivy_small_container{
                    width: 100%;
                    margin: 0 auto;

                    .ivy_heading{
                        @include slide_from_top_start();
                        .ivy_slogan{
                            color: $blue;
                            padding-bottom: 1.5rem;
                        }
                        .ivy_title{
                            font-size: 3.5rem;
                            padding-bottom: 1rem;
                        }
                        .ivy_desc{
                            padding-bottom: 2rem
                        }
                    }

                    .ivy_heading.slide_from_top{
                        @include slide_end();
                    }
                    .carousel__item {
                        @include flex(column, center, center, nowrap);
                        height: 100%;
                        padding: 2rem;
                        border: 2px solid $grey;
                        color: $purple;
                        font-size: 20px;
                        border-radius: 20px;
                        position: relative;
                        .ivy_icon_box{
                            width: 140px;
                            height: 140px;
                            border-radius: 50%;
                            background-color:#FFF5F0;
                            display: flex;
    
                            img{
                                object-fit: contain;
                                display: block;
                                margin: auto;
                            }
                        }
                        h1{
                            margin: 1rem 0;
                            font-size: 2rem;
                        }
                        .ivy_index_banner{
                            position: absolute;
                            display: flex;
                            align-items: flex-end;
                            background-color: $grey;
                            top: 0;
                            right: 10%;
                            padding: 0 1rem 1rem;
                            border-bottom-left-radius: 1rem;
                            border-bottom-right-radius: 1rem;
                            height: 100px;
                            color: $darkGrey;
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
    
                    .ivy_carousel_nav{
                        display: flex;
                        column-gap: 10px;
                        margin-top: 10px;
                        button{
                            @include flex();
                            border: 1px solid $darkGrey;
                            border-radius: 50%;
                            color: $darkGrey;
                            padding: 1rem;
                            font-size: 1.3rem;
                            background: none;
                            width: 50px;
                            height: 50px;
                            cursor: pointer;
                            transition: all 0.2s linear;
    
                            &:hover{
                                background-color: $orange;
                                border-color: $orange;
                                color: $white;
                            }
                        }
                    }
                }
            }
            .ivy_rocket{
            position: absolute;
            right: 5px;
            bottom: 5px;
            height: 200px;
            z-index: -1;
            display: block;
            }
        }
    }

    @media only screen and (max-width: 1200px){
        #ourProcess .container_size{
            flex-direction: column-reverse;

            .ivy_left_side{
                width: 100%;
                height: 500px;
                margin-top: 100px;
                margin-bottom: 100px;
                
                img{
                    width: 70%;
                    left: 50%;
                }
            }
            .ivy_right_side{
                width: 100%;
            }
        }
    }

    @media only screen and (max-width: 992px){
        #ourProcess .container_size .ivy_left_side{
            height: 300px;
        }

    }

    @media only screen and (max-width: 767px){
        #ourProcess .container_size .ivy_left_side{
            height: 200px;
        }
    }

    @media only screen and (max-width: 576px){
        #ourProcess .container_size .ivy_rocket{
            display: none;
        }
    }

</style>
