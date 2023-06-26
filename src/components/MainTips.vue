<script>
    export default {
        name: 'MainNumbersSection',
        data() {
            return {
                anidioNumbers: [
                    {
                        name: 'Projects done',
                        amount: '700+'
                    },
                    {
                        name: 'Happy Clients',
                        amount: '250+'
                    },
                    {
                        name: 'Team Members',
                        amount: '25+'
                    },
                    {
                        name: 'Years on the market',
                        amount: '12+'
                    },
                ],
            }
        },
    }
</script>

<template>
    <section id="yourTips">
        <div class="container_size">
        <div class="ivy_small_container">
            <h2>We Create New Worlds!</h2>
            <h1>Want Tips On Your Storytelling?</h1>
            <p>Join our newsletter for tips on how to elevate your brand through storytelling</p>         
        </div>


            <div class="ivy_email">
                <input type="email" placeholder="Enter you email">
                <button type="submit">Submit</button>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixin' as *;
    #yourTips{
        background-image: url(../assets/counter-bg.png);
        background-size: cover;
        color: $white;
        padding: 100px 0;
        text-align: center;

        .ivy_small_container{
            width: 60%;
            margin: 0 auto;
            padding-bottom: 50px;
            h1{
                font-size: 3.5rem;
                margin-bottom: 1rem;
            }
    
            h2{
                color: $orange;
                padding-bottom: 1.5rem;
            }
        }

    }
</style>
