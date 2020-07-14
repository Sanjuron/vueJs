<template>
<ul class="liste">
    <!-- v-bind pour créer un index à chaque fruit ainsi chaque el a une clé unique -->
    <li v-for='(fruits, index) in fruits' v-bind:key='index'>{{fruits}}</li>
</ul>
</template>

<script>

    export default {
        name: "List",
        data(){
            return{
                fruits : ['orange', 'banane', 'fraise']
            }
        }
    }

</script>

// scoped pour donner une portée locale et pas globale et src ds balise pour importer css avec scope
<style scoped src="./List.css">


</style>