<script>
    export default {
        name: 'MainGallery',
    }
</script>

<template>
    <section id="ourWorks">
        <div class="container_size">
            <div class="ivy_small_container">
                <h2 class="ivy_slogan">Our Works</h2>
                <h1 class="ivy_title">Featured Productions</h1>
                <p>Here's just a small sample of some of those projects that we're quite proud of. If you're looking for something specific feel free to get in contact with us.</p>
            </div>
            <div class="ivy_cards">
                <div class="ivy_card">
                    <img src="../assets/work1.png" alt="work number 1">
                </div>
                <div class="ivy_card">
                    <img src="../assets/work2.png" alt="work number 2">
                </div>
                <div class="ivy_card">
                    <img src="../assets/work3.png" alt="work number 3">
                </div>
                <div class="ivy_card">
                    <img src="../assets/work4.png" alt="work number 4">
                </div>
            </div>
            <button>See Our Work</button>
        </div>
    </section>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixin' as *;
    #ourWorks{
        padding: 100px 0;
        text-align: center;
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

        .ivy_cards{
            @include flex(row, center, center, wrap);
            padding: 2rem;
            gap: 1rem;

            .ivy_card{
                width: calc((100% / 2) - 0.5rem);

                img{
                    width: 100%;
                }
            }

        }

        button{
            border: 1px solid $pink;
            padding: 0.9rem 2.2rem;
            font-size: 1.2rem;
            color: $purple;
            background: none;
            border-radius: 35px;
            margin-top: 1rem;
        }
    }

</style>
