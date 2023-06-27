<script>
    import 'vue3-carousel/dist/carousel.css'
    import { Carousel, Slide } from 'vue3-carousel';
    import { ref } from 'vue';
    const myCarousel = ref(null);
    export default {
        name: 'MainTeam',
        components: {
            Carousel,
            Slide,
        },
        data() {
            return {
                teamList: [
                    {
                        name: 'Robert Coleman',
                        position: 'Owner & Creative Director',
                        pfp: '../assets/team1.png',
                        facebook: '#',
                        twitter: '#',
                        instagram: '#',
                    },
                    {
                        name: 'Don Woods',
                        position: 'Administator',
                        pfp: '../assets/team2.png',
                        facebook: '#',
                        twitter: '#',
                        instagram: '#',
                    },
                    {
                        name: 'Tomas Nash',
                        position: '2d animator & Compositor',
                        pfp: '../assets/team4.png',
                        facebook: '#',
                        twitter: '#',
                        instagram: '#',
                    },
                    {
                        name: 'Hector Vargas',
                        position: 'Project Lead & Senior Animator',
                        pfp: '../assets/team2.png',
                        facebook: '#',
                        twitter: '#',
                        instagram: '#',
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
    <section id="ourTeam">
        <div class="container_size">
            <div class="ivy_small_container">
                <h2 class="ivy_slogan">Anidio Magic Team Member</h2>
                <h1 class="ivy_title">Let Us Animate Your Project</h1>
                <p>We create new worlds!Let’s collaborate and create engaging, effective, award-winning animations</p>
            </div>
            <Carousel
                ref="myCarousel"
                :items-to-show="4" 
                :wrap-around="true" 
                :autoplay="2000" 
                :pauseAutoplayOnHover="true" 
                :snapAlign="'start'">
                    <Slide v-for="member in teamList" :key="member">
                        <div class="carousel__item">
                            <div class="ivy_card">
                                <div class="ivy_icon_box">
                                    <img :src="getImagePath(member.pfp)" :alt="member.name + 'Profile picture'">
                                </div>
                                <h1>{{ member.name }}</h1>
                                <h2>{{ member.position }}</h2>
                                <div class="ivy_social_box">
                                    <a :href="member.facebook">
                                        <i class="fa-brands fa-facebook-f"></i>
                                    </a>
                                    <a :href="member.twitter">
                                        <i class="fa-brands fa-twitter"></i>                
                                    </a>
                                    <a :href="member.instagram">
                                        <i class="fa-brands fa-instagram"></i>
                                    </a>
                                </div>
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
    </section>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixin' as *;
    #ourTeam{
        padding-bottom: 100px;
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
        .carousel__item {
            @include flex(column, center, center, nowrap);
            margin-top: 100px;
            padding: 2rem 1.5rem;
            color: $purple;
            font-size: 20px;
            border-radius: 20px;
            position: relative;
            background-color: $beige;
            width: 100%;
            .ivy_icon_box{
                width: 200px;
                height: 200px;
                background-color:#FFF5F0;
                position: absolute;
                left: 50%;
                bottom: 100%;
                transform: translate(-50%, 70%);
                img{
                    width: 100%;
                    display: block;
                }
            }
            h1{
                margin-top: 10rem;
                margin-bottom: 1rem;
                font-size: 2rem;
            }
            h2{
                margin-bottom: 1rem;
                font-size: 1rem;
                font-weight: 400;
            }
            .ivy_social_box a{
                display: inline-block;
                color: $blue;
                border: 1px solid $darkGrey;
                padding: 0.6rem;
                border-radius: 50%;
                margin: 0 0.5rem;
                width: 40px;
                height: 40px;
                text-align: center;
                transition: all 0.3s ease;

                &:hover{
                    border-color: $orange;
                    color: $white;
                    background-color: $orange;
                }
            }
        }
        .ivy_carousel_nav{
                        display: flex;
                        justify-content: center;
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
        .carousel__slide {
            padding: 10px;
        }
        .carousel__prev,
        .carousel__next {
            box-sizing: content-box;
            border: 5px solid transparent;
        }
    }
</style>
