<template>
  <div >
    <div v-for="(dom,index) in domandaRandom" :key="index">
      {{dom}}
    </div>
  </div>
</template>

<script>
export default {
  name: 'Question',
  props: {
    
  },
  data() {
        return {
          domandaRandom: [],
    domande: [
            {
              domanda: "Quante champions ha vinto il Milan?",
              id: 1
            },
            {
              domanda: "La capitale della Romania?",
              id: 2
            },
            {
              domanda: "Chi ha scoperto l'America?",
              id: 3
            },
            {
              domanda: "Quando è iniziata la prima guerra mondiale?",
              id: 4
            },
            {
              domanda: "Chi era il frontman dei Queen?",
              id: 5
            },
            {
              domanda: "A quale temperatura bolle l'acqua?",
              id: 6
            },
            {
              domanda: "Chi ha vinto gli europei nel 2021?",
              id: 7
            },
            {
              domanda: "Quale di queste è una funzione?",
              id: 8
            },
            {
              domanda: "Come si passano dati ad un componente figlio in Vue?",
              id: 9
            },
            {
              domanda: "Quante champions ha vinto la Juve?",
              id: 10
            },
          ], 
        }
    },
    mounted(){
      this.nuovaDomanda()
    },
    methods:{
        getRandomDomanda(max) {
        return Math.floor(Math.random() * (max-1)+1)
        },
        
        nuovaDomanda(){
          let numeroRandom= this.getRandomDomanda(this.domande.length)
          this.domande.forEach(el=>{
            if(el.id == numeroRandom){
              this.domandaRandom.push(el.domanda)
            }
          })
        }
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
