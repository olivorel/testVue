<template>
    <div class="first-container">
        <div class="header">
            <div class="buttons">
                <div class="button" @click="$router.go(-1)">
                    Précédent
                </div>
                <div class="button" @click="$router.push({name: 'exercice2'})">
                    Suivant
                </div>
            </div>
            <div class="title">
                Ton premier défi, la TODO list.
            </div>
            <div class="content">
                <p>Si tu es familier de cet exercice, cela ne devrait pas poser de problème.</p>
                <p>Sinon l'exercice consiste à créer une liste, qui s'implémentera avec les valeurs que tu rentreras dans un input</p>
                <p>(bonus: créer un bouton pour supprimer un élément)</p>
            </div>
        </div>
        <div class="body">
            <div class="left">
                <ul class="themes">
                    Thèmes:
                    <li>List rendering</li>
                    <li>Data Binging</li>
                    <li>Event listener</li>
                </ul>
            </div>
            <div class="separator">
            </div>
            <div class="container">
                <div class="right">
                    <!-- ton code ici -->
                    <div>
                        <label>Saisir une tâche</label>
                        <input v-model="newTodo" @keyup.enter="addTodo">
                        <div class="wrap-list">
                            <ul class="list">
                                <li v-for="todo in todos" >
                                    <span>{{ todo.text }}</span>
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
  export default {
    data () {
      return {
        todos: [{
          text: 'ma première chose à faire'
        }, {
          text: 'ma deuxième chose à faire'
        }]
      }
    },
    methods: {
      addTodo: function () {
        let text = this.newTodo
        if (text) {
          this.todos.push({text: text})
          this.newTodo = ''
        }
      }
    }
  }
</script>
<style>
    .list li {
        margin-top: 20px;
    }
</style>
