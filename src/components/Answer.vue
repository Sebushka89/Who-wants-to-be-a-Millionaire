<template>
  <div >
    <div v-for="(risp,index) in risposte" :key="index">
    {{risp.risposta}} 
    </div>
  </div>
</template>

<script>
export default {
  name: 'Answer',
  props: {
    
  },
  data() {
        return {
          risposte: [
            {
              risposta: { a: "2", b: "5", c: "7", d: "10" },
              rispostaCorretta: "7",
            },
            {
              risposta: { a: "Bucarest", b: "Milano", c: "Berlino", d: "Oslo" },
              rispostaCorretta: "Bucarest",
            },
            {
              risposta: {
                a: "Cristoforo Colombo",
                b: "Carlo Pellegatti",
                c: "216",
                d: "Amerigo Vespucci",
              },
              rispostaCorretta: "Cristoforo Colombo",
            },
            {
              risposta: { a: "1993", b: "1910", c: "1915", d: "1879" },
              rispostaCorretta: "1915",
            },
            {
              risposta: {
                a: "Zlatan",
                b: "Er Freddo",
                c: "Otello Lupacchini",
                d: "Freddy Mercury",
              },
              rispostaCorretta: "Freddy Mercury",
            },
            {
              risposta: { a: "10°", b: "5°", c: "70°", d: "100°" },
              rispostaCorretta: "100°",
            },
            {
              risposta: { a: "Spagna", b: "Germania", c: "Italia", d: "Danimarca" },
              rispostaCorretta: "Italia",
            },
            {
              risposta: {
                a: "let item = 23",
                b: "function getItem() ...",
                c: "return",
                d: "string.join()",
              },
              rispostaCorretta: "function getItem() ...",
            },
            {
              risposta: { a: "Props", b: "Emit", c: "Componenti", d: "Altro" },
              rispostaCorretta: "Props",
            },
            {
              risposta: { a: "2", b: "5", c: "7", d: "10" },
              rispostaCorretta: "2",
            },
          ],
        }
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
