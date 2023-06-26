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
        <button class="pink_btn">
            <a href="#">Start a Project</a>
        </button>
        <button>
            <a href="#">Portfolio</a>
        </button>
        <div class="ivy_hero">
            <img src="../assets/middle.png" alt="">
        </div>
    </section>
</template>

<style lang="scss">
    @use '../styles/partials/variables' as *;

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

        .ivy_hero{
            width: 100%;
            margin-top: 80px;
            img{
                width: 100%;
            }
        }
    }
</style>
