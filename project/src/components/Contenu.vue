<template>
<div class="container mt-5">

    <list v-bind:myArr="myArr" :txt="txt"></list>
    <list v-bind:myArr="myArr" :txt="txt"></list>
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
                txt: 'Salut'
            }
        },
        components: {
            'list': List
        }
    }
</script>

<style></style>
