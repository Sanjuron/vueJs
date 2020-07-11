Vue JS
======


Si l'on veut utiliser Vue JS de façon simple, il faut inclure le **CDN** dans le `index.html` :

    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>

l'instance sert à lier le code html à des méthodes, données, et à renvoyer un template. On crée une instance entre deux balises script grâce à l'objet `new Vue({})`. En général on ne crée qu'une instance qui contient toute l'application. Il faut ensuite lier l'instance dans l'objet new Vue grâce à un `id`.

    <div id="App">
        <h1> Mon application </h1>
    </div>

    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    <script>
        new Vue({
            el: '#App'
        })
    </script>


**data binding** = lier des attributs en html à Vue. Il faut pour cela ajouter **`v-bind:`** devant l'attribut (`href` ou `src` par exemple).

