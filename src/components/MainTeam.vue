<script>
    import 'vue3-carousel/dist/carousel.css'
    import { Carousel, Slide, Pagination } from 'vue3-carousel';
    import { ref } from 'vue';
    const TeamCarousel = ref(null);
    export default {
        name: 'MainTeam',
        components: {
            Carousel,
            Slide,
            Pagination
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
                breakpoints: {
                    767: {
                        itemsToShow: 2,
                        snapAlign: 'start'
                    },
                    992: {
                        itemsToShow: 3,
                        snapAlign: 'start'
                    },
                    1400: {
                        itemsToShow: 4,
                        snapAlign: 'start'
                    }
                }
            }
        },
        mounted() {
            this.TeamCarousel = this.$refs.TeamCarousel;
            this.observeTitle();
        },
        methods: {
            prev(){
                this.TeamCarousel.prev()
            },
            next(){
                this.TeamCarousel.next()
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
                const titles = document.querySelectorAll('.ivy_small_container')
                titles.forEach(title => observer.observe(title));
            },
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
                ref="TeamCarousel"
                :breakpoints="breakpoints"
                :items-to-show="1" 
                :wrap-around="true" 
                :autoplay="2000" 
                :pauseAutoplayOnHover="true" 
                :snapAlign="'center'">
                <Slide v-for="member in teamList" :key="member">
                    <div class="carousel__item">
                        <div class="ivy_card">
                            <div class="ivy_icon_box">
                                <img :src="getImagePath(member.pfp)" :alt="member.name + 'Profile picture'" loading="lazy">
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
                <template #addons>
                    <div class="ivy_carousel_nav">
                        <button @click="prev">
                            <i class="fa-solid fa-arrow-left"></i>
                        </button>
                        <Pagination />
                        <button @click="next">
                            <i class="fa-solid fa-arrow-right"></i>
                        </button>
                    </div>
                </template>
            </Carousel>

        </div>
        <!--BACKGROUND IMAGES-->
        <img src="../assets/shape.png" alt="red mega dot" id="red_circle_left" loading="lazy">
        <img src="../assets/shape2.png" alt="red mega dot" id="red_circle_right" loading="lazy">
    </section>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixin' as *;
    #ourTeam{
        padding-bottom: 100px;
        position: relative;
        .ivy_small_container{
            width: 60%;
            margin: 0 auto;
            text-align: center;
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

        .ivy_small_container.slide_from_top{
            @include slide_end();
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
            @include flex();
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
                margin-top: 0.6rem;

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

        #red_circle_left{
            position: absolute;
            display: block;
            left: 0;
            top: 10%;
            z-index: -2;
            animation: zoominout 3s linear infinite;
        }
        @keyframes zoominout {
            0%{
                transform: scale(1);
            }
            50%{
                transform: scale(0.9);
            }
            100%{
                transform: scale(1);
            }
        }
        #red_circle_right{
            position: absolute;
            display: block;
            right: -20px;
            top: 10%;
            transform: translateY(-50%);
            z-index: -2;
            animation: slidein 3s linear infinite;
        }
        @keyframes slidein {
            0%{
                transform: translateX(0);
            }
            50%{
                transform: translateX(-25px);
            }
            100%{
                transform: translateX(0);
            }
        }

    }
    @media only screen and (max-width: 992px){
        #ourTeam .ivy_small_container{
            width: 100%;
        }
    }
    @media only screen and (max-width: 576px){
        #ourTeam #red_circle_left{
            display: none;
        }
    }

</style>
