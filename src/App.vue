<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <Header :quote-count="quotes.length" :max-quotes="maxQuotes"></Header>
    <NewQuote @quoteAdded="newQuote($event)"></NewQuote>
    <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quote-grid>
<div class="row">
    <div class="col-sm-12 text-center">
      <div class="alert alert-info">Info: Click on quote to delete it</div>
    </div>

    </div>
  </div>
</template>

<script>

  import QuoteGrid from "@/components/QuoteGrid";
  import NewQuote from "@/components/NewQuote";
  import Header from "@/components/Header"

export default {
  name: 'app',
  data: () => ({
    quotes: ['Joe\'s first quote!'],
    maxQuotes: 10
  }),
  components: {
    'app-quote-grid': QuoteGrid,
    NewQuote, Header
  },

  methods: {
    newQuote(quote){
      this.quotes.push(quote);
    },

    deleteQuote(index){
      this.quotes.splice(index, 1);
    }
  }
}
</script>

<style>


  #app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
