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

Les **directives** permettent d'effectuer des actions sur les **templates**; le **DOM**
**`v-on`** est une directive pour créer des événements : `mouvemove` `click`. 

    // dans la div de l'application
    v-on:click='handleClick' // pour créer un événement click

    //dans le script, dans methods, log tous les événements associés à la directive click
    handleClick : function(e){
        console.log(e)
    }

Les Events Modifiers
-------------------

`.once` est un exemple d'*event modifier* Si on l'ajoute à une directive, alors celle-ci ne s'exécute qu'une fois

    v-on:click.once // un seul clic est pris en compte

`.stop` stoppe la propagation des événements

`.prevent` empêche le rechargement de la page

Les Key Modifiers
-----------------

**Un événement qui ne s'active que si l'on appuie sur une touche (key) en particulier.** 

    v-on:keyup // key modifier qui enregistre les touches appuyées

[liste des key modifiers](https://fr.vuejs.org/v2/guide/events.html)

----------------------

**2-way data binding** grâce à `v-model`

    v-html='' est une directive pour entrer du html brut dans un template

**computed** est un mot-réservé qui permet de ne lancer qu'une fois les fonctions qui se trouvent à l'intérieur. 

**watch** autre mot-réservé va lancer une fonction seulement quand une des propriétés de nos données vont changer

*toggle* veut dire basculement

Pour le **inline css**, respecter les conventions:
- varialbe entre **guillemets**, valeur de lapropriété entre **apostrophes**
- si nom de propriété composé, alors **camelCase**

La balise **`template`** sert à faire des **rendus conditionnels de groupe**. Cette balaise n'apparaît pas dans le DOM.

`v-for` est une directive permettant de faire **une boucle for**
Pour afficher les tableaux d'objets, il faut faire un v-for dans un v-for ex:

    		<ul>
			<!-- syntaxe pour afficher les tableaux d'objets -->
			<li v-for="item in japanMovie">
				<div v-for="(val, props) in item">{{props}} : {{val}}</div>
			</li>
		    </ul>
