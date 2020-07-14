<template>
<div>
    <p>
        {{txt}}
    </p>
    <list v-bind:firstname="firstname"></list>
</div>

</template>

<script>
    import List from './List';

    export default {
        name: "Contenu",
        // raccourci ES6 pour data : function(){}
        data() {
            return {
                txt: "je suis le contenu",
                firstname: "sanjuron",
            }
        },
        components: {
            'list': List
        }
    }
</script>

<style></style>
