<template>
    <div >
      <div class="container">
        <div class="row">
          <div v-for="(risp,index) in domandarispostaRandom.risposta" :key="index" class="col-6">
            <div class="btn-success mt-3"  @click="$emit('checkAnswer',risp )">{{risp}}</div>
          </div>
        </div> 
      </div>
    </div>  
</template>

<script>
export default {
  name: 'Answer',
  props: {
    domandarispostaRandom: Object,
  },
  data() {
        return {
        }
    },
    mounted(){
    },
    methods:{
       
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
