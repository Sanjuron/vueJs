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
    created(){
        bus.$on('changeTitle', (data) => {
            this.title = data
        })
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