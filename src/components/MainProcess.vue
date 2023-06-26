<script>
    export default {
        name: 'MainProcess',
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
                    <p>We have an effective process for working on animation</p>
                </div>
            </div>

        </div>
    </section>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixin' as *;
    #ourProcess{
        padding: 100px 0;

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
                }
            }
            .ivy_right_side{
                width: 50%;
            }
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
            }
        }
    }

</style>
