<template>
    <div class="donnee" v-if="donnee">
        <p>{{donnee.title}}</p>
        <p> {{donnee.content}}</p>
        <p>{{donnee.question}}</p>
    </div>

</template>
<script>
  export default {
    data () {
      return {
        donnee: {
          title: 'Mon super composant',
          content: 'Je suis utilisable où tu veux!!',
          question: 'Classe ou pas classe ?'
        }
      }
    },
    methods: {},
    components: {}
  }
</script>