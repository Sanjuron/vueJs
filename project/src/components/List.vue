<template>
<div>
<ul class="liste">
    
    <li v-for='(film, index) in myArr' v-bind:key='index'>
        <div class="card">
            <div class="card-body">
        Titre: {{film.titre}}
        <br>
        Date: {{film.date}}
        </div>
        </div>
    </li>
</ul>
<p>{{txt}} </p>
<div class="btn btn-danger mt-2" v-on:click="delMovie()">Supprime le film</div>
<div class="btn btn-danger mt-2 ml-2" v-on:click="delTxt()">Supprime le txt</div>
<div class="btn btn-danger mt-2 ml-2" v-on:click="changeTitle">Modifier le titre</div>

</div> 

</template>

<script>

    export default {
        name: "List",
        data(){
            return{
                fruits : ['orange', 'banane', 'fraise']
            }
        },
        methods: {
            delMovie: function(){
                this.myArr.pop();
            },
            delTxt: function(){
            this.txt="";
            },
            changeTitle: function(){
                this.$emit('changeTitle', "Mon nouveau titre") //emit sert à créer un événement personnalisé auquel le parent peut écouter
            }
        },
        //il faut recevoir les props
        props: ['myArr', "txt"]
         
    }

</script>

// scoped pour donner une portée locale et pas globale et src ds balise pour importer css avec scope
<style scoped src="./List.css">


</style>