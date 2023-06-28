<script>
    export default {
        name: 'FooterNavbar',
        data() {
            return {
                navLinks: [
                    {
                        title: 'About us',
                        link: '#'
                    },
                    {
                        title: 'Portfolio',
                        link: '#'
                    },
                    {
                        title: 'Pricing',
                        link: '#'
                    },
                    {
                        title: 'Career',
                        link: '#'
                    },
                    {
                        title: 'Contact',
                        link: '#'
                    },
                ],
            }
        },
    }
</script>

<template>
    <div class="container_size">
        <nav>
            <div class="ivy_logo_box">
                <img src="../assets/footer-logo.png" alt="Anidio Logo" loading="lazy">
            </div>
            <ul class="ivy_nav_menu">
                <li class="ivy_nav_item" v-for="link in navLinks">
                    <a :href="link.link">{{ link.title }}</a>
                </li>
            </ul>
        </nav>
        <section id="copyright">
            <p>
                Copyright © 2022 <a href="#">Softivus.</a> All rights reserved.
            </p>
            <div class="ivy_social_box">
                <a href="#">
                    <i class="fa-brands fa-facebook-f"></i>
                </a>
                <a href="#">
                    <i class="fa-brands fa-twitter"></i>                
                </a>
                <a href="#">
                    <i class="fa-brands fa-instagram"></i>
                </a>
            </div>
        </section>
    </div>
    
</template>

<style lang="scss" scoped>
    @use '../styles/partials/mixin' as *;
    @use '../styles/partials/variables' as *;

    .container_size{
        padding-top: 3rem;      
        nav{
            @include flex(row, space-between, center, nowrap);
            padding: 1rem 0;
            border-bottom: 1px solid $darkGrey;
    
            .ivy_nav_menu{
                @include flex(row, center, center, wrap);
    
                .ivy_nav_item{
                    margin: 0 0.6rem;
                    a{
                        color: $purple;
                        font-weight: bold;
                        font-size: 1.2rem;
                        transition: all 0.3s ease;
                        &:hover{
                            color: $blue;
                        }
                    }
                }
            }
        }
        
        #copyright{
            color: $darkGrey;
            padding: 2rem 0;
            @include flex(row, space-between, center, nowrap);
            p a{
                color: blue;
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
    }
    @media only screen and (max-width: 767px) {
        .container_size #copyright{
            @include flex(column-reverse, space-between, center, nowrap);

            .ivy_social_box a{
                margin: 0 0.5rem 1rem;
            }
        }

        .container_size nav{
            @include flex(column, space-between, center, nowrap);

            img{
                margin-bottom: 1rem;
            }
        }
    }
</style>
