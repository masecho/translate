<template>
  <div class="translateOutput">
    <h4>{{translateText}}</h4>
  </div>
</template>

<script>
  export default {
    name: 'translateOutput',
    props:{
      translateText:{
          type:String,
          default:""
      }
    }


  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
