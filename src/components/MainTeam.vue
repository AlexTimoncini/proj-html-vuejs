<script>
    export default {
        name: 'MainTeam',
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
        </div>
    </section>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixin' as *;
    #ourTeam{
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
