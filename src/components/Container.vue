<template>
  <div>
    <Question />
    <Answer />
  </div>
</template>

<script>
import Question from './Question.vue';
import Answer from './Answer.vue';
export default {
  name: 'Container',
  components: {
    Question,
    Answer,
  }, 
  props: {
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
