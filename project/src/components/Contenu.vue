<template>
<div class="container mt-5">

    <h1> {{title}} </h1>
    <list v-bind:myArr="myArr" :txt="txt" >
        Patientez
        <template v-slot:info>
                        <h1>Le contenu du slot nommé</h1>
        </template>
    </list>
</div>

</template>

<script>
    import List from './List';

    export default {
        name: "Contenu",
        // raccourci ES6 pour data : function(){}
        data() {
            return {
                myArr: [
                    {titre: "Jaws", date: 1975},
                    {titre: "Goodfellas", date: 1990},
                    {titre: "Barberousse", date: 1965},
                ],
                txt: 'Salut',
                title: 'Ceci est un titre'
            }
        },
        methods : {
            // changeTitle: function(newTitle){
            //     this.title = newTitle;
            // }
        },
        components: {
            'list': List
        }
    }
</script>

<style>
h1{
    margin-top : 100px!important;
}
</style>
