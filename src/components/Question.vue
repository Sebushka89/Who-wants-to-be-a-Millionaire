<template>
  <div>
      {{questions}}
  </div>
</template>

<script>
export default {
  name: 'Question',
  props: {
    
  },
  data() {
        return {
           questions:["1- Come ti chiami?", "2- 2+2?", "3- quanti anni hai?"] 
        }
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
