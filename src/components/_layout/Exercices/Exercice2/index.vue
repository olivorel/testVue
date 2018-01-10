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
      Liste des composants :<span @click="changeTheDisplayedComponent('composant1')">composants1</span><span
            @click="changeTheDisplayedComponent('composant2')">composants2</span><span @click="changeTheDisplayedComponent('composant3')">composants3</span>
      <!-- ton code ici -->
      <div class="Listcomponents">
        <ul>
          <li v-if="list"><component1></component1></li>
          <!--<li v-if="list"><component2></component2></li>-->
          <!--<li v-if="list"><component3></component3></li>-->
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
        list: false
      }
    },
    methods: {
      changeTheDisplayedComponent: function () {
        this.list = true
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
</style>
