<script>
    import { Carousel, Slide } from 'vue3-carousel';
    import { ref } from 'vue';
    const myCarousel = ref(null);
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
            }
        },
        mounted() {
            this.myCarousel = this.$refs.myCarousel;
        },
        methods: {
            prev(){
                this.myCarousel.prev()
            },
            next(){
                this.myCarousel.next()
            },
            getImagePath: function(imgPath) {
                return new URL(imgPath, import.meta.url).href;
            }
        }
    }
</script>

<template>
    <section id="ourProcess">
        <div class="container_size">
            <div class="ivy_left_side">
                <img src="../assets/process-thumb.png" alt="user riding a rocket">
            </div>
            <div class="ivy_right_side">
                <div class="ivy_small_container">
                    <h2 class="ivy_slogan">Our Process</h2>
                    <h1 class="ivy_title">Our Process for Your Animation Production</h1>
                    <p class="ivy_desc">We have an effective process for working on animation</p>
                    <Carousel
                    ref="myCarousel"
                    :items-to-show="2" 
                    :wrap-around="true" 
                    :autoplay="2000" 
                    :pauseAutoplayOnHover="true" 
                    :snapAlign="'start'">
                        <Slide v-for="slide, index in processList" :key="slide">
                            <div class="carousel__item">
                                <div class="ivy_icon_box">
                                    <img :src="getImagePath(slide.img)" :alt="slide.name">
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
            <img src="../assets/smart4.png" alt="yellow rocket" class="ivy_rocket">

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



</style>
