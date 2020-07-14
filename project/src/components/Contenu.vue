<template>
<div>
    <p>
        {{txt}}
    </p>
    <list></list>
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
            }
        },
        components: {
            'list': List
        }
    }
</script>

<style></style>
