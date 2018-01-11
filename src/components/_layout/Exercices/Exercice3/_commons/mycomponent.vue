<template>
    <div class="donnee" v-if="donnee">
        <p v-model="donnee.title">{{donnee.title}}</p>
        <p v-model="donnee.content"> {{donnee.content}}</p>
        <p v-model="donnee.question">{{donnee.question}}</p>
    </div>

</template>
<script>
  export default {
    data () {
      return {}
    },
    methods: {},
    components: {}
  }
</script>