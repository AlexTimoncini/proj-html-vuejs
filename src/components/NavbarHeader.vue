<script>
    export default {
        name: 'NavbarHeader',
        data() {
            return {
                navLinks: [
                    {
                        title: 'Home',
                        link: '#'
                    },
                    {
                        title: 'About us',
                        link: '#'
                    },
                    {
                        title: 'Portfolio',
                        link: '#'
                    },
                    {
                        title: 'Our process',
                        link: '#'
                    },
                    {
                        title: 'Pricing',
                        link: '#'
                    },
                    {
                        title: 'Blog',
                        link: '#'
                    },
                    {
                        title: 'Contact',
                        link: '#'
                    },
                ],
            }
        },
        methods: {
            displayMenu(){
                const ulMenu = document.querySelector('.ivy_nav_menu')
                ulMenu.classList.toggle('visible')
            }
        },
    }
</script>

<template>
    <nav>
        <div class="container_size">
            <div class="ivy_logo_box">
                <img src="../assets/logo.png" alt="Anidio Logo" loading="lazy">
            </div>
            <ul class="ivy_nav_menu">
                <li class="ivy_nav_item" v-for="link in navLinks">
                    <a :href="link.link">{{ link.title }}</a>
                </li>
                <li class="pink_btn">
                    <a href="#">Get A Quote</a>
                </li>
            </ul>
            <button @click="displayMenu" class="ivy_nav_toggle">
                <i class="fa-solid fa-bars-staggered"></i>
            </button>
        </div>
    </nav>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/mixin' as *;
    @use '../styles/partials/variables' as *;

    nav{
        padding: 1rem 0.2rem;
        position: relative;
        .container_size{
            @include flex(row, space-between, center, nowrap);
            .ivy_nav_menu{
                @include flex();
                .ivy_nav_item{
                    margin: 0 0.6rem;
    
                    a{
                        color: $white;
                        font-weight: bold;
                        font-size: 1.2rem;
                    }
                }
    
                .pink_btn{
                    padding: 0.9rem 1.9rem;
                    background-color: $pink;
                    border-radius: 35px;
                    margin-left: 0.6rem;
    
                    a{
                        color: $purple;
                        font-weight: bold;
                        font-size: 1.2rem;
                    }
                }
            }

            .ivy_nav_toggle{
                border: none;
                background: none;
                color: $white;
                display: none;
                font-size: 1.6rem;
                padding-right: 0.3rem;
                cursor: pointer;
            }
        }
    }

    /**MEDIA QUERIES**/
    @media only screen and (max-width: 992px){    
        nav .container_size .ivy_nav_menu{
            @include flex(column, center, center, nowrap);
            position: absolute;
            top: 100%;
            left: 0;
            width: calc(100% - 2rem);
            background-color: $purple;
            z-index: 1;
            transform: translateY(-50px);
            opacity: 0;
            transition: transform 0.5s ease;
        }

        nav .container_size .ivy_nav_menu.visible{
            height: auto;
            opacity: 1;
            transform: translateY(0px);
            margin: 0 1rem;
            padding: 0.5rem 1rem;
            align-items: flex-start;
            border-bottom-left-radius: 20px;
            border-bottom-right-radius: 20px;
        }

        nav .container_size .ivy_nav_menu.visible .ivy_nav_item{
            border: 1px solid $darkGrey;
            margin: 0.5rem 0;
            padding: 0.8rem;
            width: 100%;
            text-align: start;
        }

        nav .container_size .ivy_nav_toggle{
            display: block;
            z-index: 2;
        }
    }

    @media only screen and (max-width: 1200px){
        nav .container_size .ivy_nav_menu .ivy_nav_item{
            margin: 0 0.4rem;
        }
    }
</style>
