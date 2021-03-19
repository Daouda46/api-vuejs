<template>

<div>
    <h1>Voici la Page 2</h1>

    <h3 @click="retourAcc" class="btn btn-success" >Aller a l'accueil</h3>
</div>
</template>

<script>
    export default{
        name:'Page2',
        data(){

        },
        methods:{
            retourAcc:function(){
                this.$router.push('/')
            }
        }
    }
</script>

<style>

</style>