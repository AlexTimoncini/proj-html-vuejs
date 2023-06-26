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
    }
</script>

<template>
    <nav class="container_size">
        <div class="ivy_logo_box">
            <img src="../assets/logo.png" alt="Anidio Logo">
        </div>
        <ul class="ivy_nav_menu">
            <li class="ivy_nav_item" v-for="link in navLinks">
                <a :href="link.link">{{ link.title }}</a>
            </li>
            <li class="pink_btn">
                <a href="#">Get A Quote</a>
            </li>
        </ul>
    </nav>
</template>

<style lang="scss">
    @use '../styles/partials/mixin' as *;
    @use '../styles/partials/variables' as *;

    nav{
        @include flex(row, space-between, center, nowrap);
        padding: 1rem 0;

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
    }
</style>
