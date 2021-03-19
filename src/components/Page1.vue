<template>

<div>
    <h1>Les articles de blog !</h1>

    <ul>
        <li v-for="(article, index) in allArticles" :key="index">
            <router-link :to="`/blogpost/${index +1}`">

                <div class="card p-3" >
                    <p>
                        UserId : {{article.userId}} <br>
                        Titre : {{article.title}} <br>
                        Body : {{article.body}}

                    </p>
                </div>
            </router-link>
        </li>
    </ul>
</div>
</template>

<script>
    import axios from 'axios'
    export default{
        name:'Page1',
        data(){
            return{
                allArticles:[]
            }
        },
        created(){
            axios
            .get('https://jsonplaceholder.typicode.com/posts')
            .then(response => {
                // console.log(response)
                this.allArticles = response.data

            })
        }
    }
</script>

<style>

</style>