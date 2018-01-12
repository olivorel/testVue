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
                                <li v-for="todo in todos">
                                    <span>{{ todo.text }}</span>
                                    <button @click="removeTodo(todo)">X</button>
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
  // exercice 1
  //  export default {
  //    data () {
  //      return {
  //        storage: {
  //          todos: [{
  //            text: 'ma première chose à faire'
  //          }, {
  //            text: 'ma deuxième chose à faire'
  //          }]
  //        }
  //      }
  //    },
  //    methods: {
  //      addTodo: function () {
  //        let text = this.newTodo
  //        if (text) {
  //          this.todos.push({text: text})
  //          this.newTodo = ''
  //        }
  //      },
  //      removeTodo: function (todo) {
  //        this.todos.splice(this.todos.indexOf(todo), 1)
  //      }
  //    }
  //  }
  // exercice 4
  Vue.use(Vuex)
  export default new Vuex.Store({
    state: {
      todos: [{
        text: 'ma première chose à faire'
      }, {
        text: 'ma deuxième chose à faire'
      }],
      newTodo: ''
    },
    mutations: {
      ADD_TODO (state) {
        state.todos.push({
          body: state.newTodo,
          completed: false
        })
      },
      REMOVE_TODO (state, todo) {
        let todos = state.todos
        todos.splice(todos.indexOf(todo), 1)
      },
    },
    actions: {
      addTodo ({commit}) {
        commit('ADD_TODO')
      },
      removeTodo ({commit}, todo) {
        commit('REMOVE_TODO', todo)
      }
    }
  })
</script>
<style>
    .list li {
        margin-top: 20px;
    }
</style>
