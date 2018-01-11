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
      return {}
    },
    methods: {},
    components: {}
  }
</script>