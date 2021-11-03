<template>
  <div >
    <div v-for="(dom,index) in domandarispostaRandom" :key="index">
      <div class="container">
        <div class="row">
          <div class="col-12">
            <div class="btn-success mt-3"  @click="$emit('checkAnswer',dom.risposta.a )">{{dom.risposta.a}}</div>
            <div class="btn-success mt-3"  @click="$emit('checkAnswer',dom.risposta.b)">{{dom.risposta.b}}</div>
          </div>
          <div class="col-12 ">
            <div class="btn-success mt-3"  @click="$emit('checkAnswer',dom.risposta.c )">{{dom.risposta.c}}</div>
            <div class="btn-success mt-3"  @click="$emit('checkAnswer',dom.risposta.d)">{{dom.risposta.d}}</div>
          </div>
        </div> 
      </div>
    </div>  
  </div>
</template>

<script>
export default {
  name: 'Answer',
  props: {
    domandarispostaRandom: Array,
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
