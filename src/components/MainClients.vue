<script>
    export default {
        name: 'MainClients',
    }
</script>

<template>
    <section id="ourClients">
        <div class="container_size">
            <div class="ivy_small_container">
                <h2 class="ivy_slogan">Why Anidio studio?</h2>
                <h1 class="ivy_title">We Love Our Clients</h1>
                <p>We are trusted throughout adland and have a wealth of recommendations from start-ups to renowned global brands.</p>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixin' as *;
    #ourClients{
        margin-top: 500px;
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
    }
</style>
