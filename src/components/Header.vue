<template>

<div>
    <ul class="nav">
        <li class="btn btn-primary btn-nav"><router-link to="/" exact >Accueil</router-link> </li>
        <li class="btn btn-primary btn-nav"> <router-link to="/page1" >Page1</router-link> </li>
        <li class="btn btn-primary btn-nav"><router-link to="/page2" >Page2</router-link></li>
    </ul>
</div>
</template>

<script>
    export default{
        name:'Header',
        data(){

        }
    }
</script>

<style>
    .btn-nav{
        margin: 5px;
    }
    .btn-nav a{
        color: #fff;
    }
    .btn-nav a:hover{
        color: #fff;
        text-decoration: none;
    }

</style>