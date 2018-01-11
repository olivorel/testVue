<template>
    <div class="first-container">
        <div class="header">
            <div class="buttons">
                <div class="button" @click="$router.go(-1)">
                    Précédent
                </div>
                <div class="button" @click="$router.push({name: 'exercice3'})">
                    Suivant
                </div>
            </div>
            <div class="title">
                Ton deuxième défi, le composant dynamique.
            </div>
            <div class="content">
                <p>Le but de cet exercice est de mettre en place un composant dynamique qui changera au clique sur un nom d'une liste.</p>
                <p>A chaque clique sur un des noms, le composant devra changer d'état.</p>
                <p>Les composants à afficher se situent dans le dossier "./_subs/" </p>
                <p>Aucun style imposé</p>
            </div>
        </div>
        <div class="body">
            <div class="left">
                <ul class="themes">
                    Thèmes:
                    <li>Dynamique Components</li>
                    <li>Event listener</li>
                </ul>
            </div>
            <div class="separator">
            </div>
            <div class="right">
                Liste des composants :
                <!-- ton code ici -->
                <div class="Listcomponents">
                    <ul>
                        <span @click="changeTheDisplayedComponent('composant1')">composants1</span>
                        <span @click="changeTheDisplayedComponent2('composant2')">composants2</span>
                        <span @click="changeTheDisplayedComponent3('composant3')">composants3</span>

                        <li v-if="show1">
                            <component1></component1>
                        </li>
                        <li v-if="show2">
                            <component2></component2>
                        </li>
                        <li v-if="show3">
                            <component3></component3>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
  import component1 from './_subs/Component1.vue'
  import Component2 from './_subs/Component2.vue'
  import Component3 from './_subs/Component3.vue'

  export default {
    data () {
      return {
        show1: false, show2: false, show3: false
      }
    },
    methods: {
      changeTheDisplayedComponent: function () {
        this.show1 = true; this.show2 = false; this.show3 = false
      },
      changeTheDisplayedComponent2: function () {
        this.show1 = false; this.show2 = true; this.show3 = false
      },
      changeTheDisplayedComponent3: function () {
        this.show1 = false; this.show2 = false; this.show3 = true
      }
    },
    components: {
      component1, Component2, Component3
    }
  }
</script>
<style>
    .right span {
        cursor: pointer;
    }

    li {
        list-style:none;
    }
</style>
