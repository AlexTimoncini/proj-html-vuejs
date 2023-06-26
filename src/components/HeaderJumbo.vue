<script>
    export default {
        name: 'HeaderJumbo',
    }
</script>

<template>
    <section id="jumbotron" class="container_size">
        <h2 class="ivy_slogan">Imagine, Create, Experience</h2>
        <h1 class="ivy_title">We Animate <br>With Ninja-Like Precision</h1>
        <p class="ivy_desc">We are a character-driven animation studio striving to make high-quality animations.</p>
        <button class="ivy_btn pink_btn">
            <a href="#">Start a Project</a>
        </button>
        <button class="ivy_btn pink_border">
            <a href="#">Portfolio</a>
        </button>
        <div class="ivy_hero">
            <img src="../assets/middle.png" alt="">
            <button class="ivy_playpause">
                <i class="fa-solid fa-play"></i>
            </button>
        </div>
    </section>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixin' as *;
    #jumbotron{
        color: $white;
        text-align: center;
        padding-top: 80px;
        .ivy_slogan{
            color: $orange;
            padding-bottom: 1.5rem;
        }

        .ivy_title{
            font-size: 4rem;
            padding-bottom: 1rem;
        }

        .ivy_desc{
            font-size: 1.3rem;
            padding-bottom: 2rem;
        }

        .ivy_btn{
            padding: 0.9rem 2.5rem;
            border-radius: 35px;
            margin-right: 1.2rem;
            border: none;

            a{
                color: $purple;
                font-weight: 400;
                font-size: 1.2rem;
            }
        }

        .pink_btn{
            background-color: $pink;
        }

        .pink_border{
            background: none;
            border: 1px solid $pink;

            a{
                color: $white;
            }
        }

        .ivy_hero{
            width: 100%;
            margin-top: 80px;
            position: relative;
            z-index: 2;
            img{
                width: 100%;
            }

            .ivy_playpause{
                @include positionCenter;
                background-color: #A616EA;
                border: none;
                height: 70px;
                width: 70px;
                border-radius: 50%;
                text-align: center;
                i{
                    font-size: 1.5rem;
                    color: $white;
                }
            }

        }
    }
</style>
