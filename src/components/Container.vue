<template>
  <div v-if="nextStep">
    <Question :domandarispostaRandom="domandaAttuale" />
    <Answer @checkAnswer="checkRisposta" :domandarispostaRandom="domandaAttuale"/>
  </div>
  <div v-else>
    <h2>per te il Grande Fratello finisce qui, coglione</h2>
    <button @click="nuovaPartita()">Gioca di nuovo coglione</button>
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
          nextStep: true,
          domandeRandomId:[],
          domandaAttuale:{},
          domandarispostaRandom: [],
          domandaAttualeId: 0,
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
                c: "Andrea Calzolari",
                d: "Amerigo Vespucci",
              },
              rispostaCorretta: "Cristoforo Colombo",
            },
            {
              domanda: "Quando è iniziata la prima guerra mondiale?",
              id: 4,
              risposta: { a: "1993", b: "1910", c: "1914", d: "1879" },
              rispostaCorretta: "1914",
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
      this.getRandomNumbers(5);
    },
    methods:{
        checkRisposta(checkAnswer) {
          if(checkAnswer == this.domandaAttuale.rispostaCorretta){
            console.log("risposta corretta")
            this.getDomandaAttuale()
          }else{
            this.nextStep = false
            //alert("risposta sbagliata, coglione")
          }
        },
        getRandomNumbers(num) {
          let max = this.domande.length
          while(this.domandeRandomId.length < num){
            let random = Math.floor(Math.random() * (max)+1)
            if(!this.domandeRandomId.includes(random)){
              this.domandeRandomId.push(random)
            }
          }
          this.getDomandaAttuale()
        },
      getDomandaAttuale(){
        this.domandaAttuale=this.domande[this.domandeRandomId[this.domandaAttualeId]]
        this.domandaAttualeId ++
        if(this.domandaAttualeId==6){
          alert("hai vinto,coglione")
        }
      },
      nuovaPartita(){
        this.nextStep = true
        this.domandaAttualeId = 0
        this.getRandomNumbers(5)
      }
    },
    computed:{
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
