<template>

    <div class="header-top">
        <p>{{title}} </p>
    </div>

</template>

<script>

import {bus} from '../main';

export default {
    name: 'Header',
    data(){
        return {
            title: "Mon titre de base"
        }
    },
    beforeCreate(){
        console.log("il va être crée");
    },
    created(){
        console.log('le composant est créé');
        bus.$on('changeTitle', (data) => {
            this.title = data
        })
    }, 
    beforeMount(){
        console.log('il va être monté dans le DOM');
    },
    mounted(){
        console.log("il est intégré dans le DOM");
    },
    beforeUpdate(){
        console.log("il va se mettre à jour");
    },
    updated(){
        console.log("Le composant s'est bien mis à jour");
    }
}

</script>


<style>
    .header-top{
        position: fixed;
        top: 0;
        height: 50px;
        background: #333;
        color: #f1f1f1;
        width: 100%;
        text-align: center;
        line-height: 50px;
        font-size: 25px;
    }

</style>