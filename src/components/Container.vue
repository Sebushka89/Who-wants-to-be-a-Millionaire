<template>
  <div>
    <Question :domandarispostaRandom="domandarispostaRandom" />
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
    
  },
  data() {
        return {
          domandarispostaRandom: [],
          domande: [
            {
              domanda: "Quante champions ha vinto il Milan?",
              id: 1,
              risposta: { a: "2", b: "5", c: "7", d: "10" },
              rispostaCorretta: "7",
            },
            {
              domanda: "La capitale della Romania?",
              id: 2,
              risposta: { a: "Bucarest", b: "Milano", c: "Berlino", d: "Oslo" },
              rispostaCorretta: "Bucarest",
            },
            {
              domanda: "Chi ha scoperto l'America?",
              id: 3,
              risposta: {
                a: "Cristoforo Colombo",
                b: "Carlo Pellegatti",
                c: "216",
                d: "Amerigo Vespucci",
              },
              rispostaCorretta: "Cristoforo Colombo",
            },
            {
              domanda: "Quando è iniziata la prima guerra mondiale?",
              id: 4,
              risposta: { a: "1993", b: "1910", c: "1915", d: "1879" },
              rispostaCorretta: "1915",
            },
            {
              domanda: "Chi era il frontman dei Queen?",
              id: 5,
              risposta: {
                a: "Zlatan",
                b: "Er Freddo",
                c: "Otello Lupacchini",
                d: "Freddy Mercury",
              },
              rispostaCorretta: "Freddy Mercury",
            },
            {
              domanda: "A quale temperatura bolle l'acqua?",
              id: 6,
               risposta: { a: "10°", b: "5°", c: "70°", d: "100°" },
              rispostaCorretta: "100°",
            },
            {
              domanda: "Chi ha vinto gli europei nel 2021?",
              id: 7,
              risposta: { a: "Spagna", b: "Germania", c: "Italia", d: "Danimarca" },
              rispostaCorretta: "Italia",
            },
            {
              domanda: "Quale di queste è una funzione?",
              id: 8,
              risposta: {
                a: "let item = 23",
                b: "function getItem() ...",
                c: "return",
                d: "string.join()",
              },
              rispostaCorretta: "function getItem() ...",
            },
            {
              domanda: "Come si passano dati ad un componente figlio in Vue?",
              id: 9,
              risposta: { a: "Props", b: "Emit", c: "Componenti", d: "Altro" },
              rispostaCorretta: "Props",
            },
            {
              domanda: "Quante champions ha vinto la Juve?",
              id: 10,
              risposta: { a: "2", b: "5", c: "7", d: "10" },
              rispostaCorretta: "2",
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
              this.domandarispostaRandom.push({domanda:el.domanda,risposta:el.risposta,id:el.id, rispostaCorretta:el.rispostaCorretta})
            }
          })
        }
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
