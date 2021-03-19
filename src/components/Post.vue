<template>

<div>
    <h1>Le post numéro {{id}} </h1>
    
    <div class="card p-3">
        Identifiant : {{articleUnique.userId}} <br> 
        Titre :  {{articleUnique.title}}  <br>

         Body : {{articleUnique.body}}

    </div>
    
</div>
</template>

<script>
    import axios from 'axios'
    export default{
        name:'Post',
        data(){
            return {
                id:this.$route.params.id,
                articleUnique:[]
            }
        },
        mounted(){
            axios
            .get(`https://jsonplaceholder.typicode.com/posts/${this.id}`)
            .then(response => {
                // console.log(response)
                this.articleUnique = response.data

            })
        }
    }
</script>

<style>

</style>