<template>
    <div class="container ">
        <h1 class="my-5">App météo avec vuejs</h1>

        <div class="form-group mb-5">
            <label for="position"> Entrez le nom d'une ville :</label>
            <input v-model="requete" v-on:keypress.enter="geMeteo" type="text" id="position" class="form-control" >
        </div>

        <div class="w-75 m-auto" v-if="temps">
            <h3 class="text-center mb-3">Position : {{temps.name}}</h3>
            <div class="card text-center p-5">
                <p class="text-affichage">
                    Température : {{temps.main.temp}} °
                </p>
                <p class="text-affichage">
                    Temps : {{temps.weather[0].description}}
                </p>
               
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios'

    export default{
        name:'Meteo',
        data(){
            return {
                requete:'',
                temps:undefined,
                api_code:'2e52862380d0a7a2fff86e64aeddd5e5',
                url_recherche:'https://api.openweathermap.org/data/2.5/weather?',
            }
        },
        methods:{
            geMeteo:function(){
                // if(e.key == 'Enter'){
                    axios
                    .get(`${this.url_recherche}q=${this.requete}&units=metric&APPID=${this.api_code}&lang=fr`)
                    .then(reponse => {
                        // console.log(reponse)
                        this.temps = reponse.data
                    })
                    this.requete=''
                // }
            }
        }

    }
</script>

<style>
    .texte-affichage{
        font-size: 30px;
        font-weight: 400;
        line-height: 1.3;
    }
</style>