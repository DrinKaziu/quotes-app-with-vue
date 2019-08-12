<template>
  <div class="container">
    <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    <app-new-quote @addQuote="newQuote"></app-new-quote>
    <app-quotes-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quotes-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">info: Click on Quote to Delete it</div>
      </div>
    </div>
  </div>
</template>

<script>
  import QuotesGrid from './components/QuotesGrid.vue';
  import NewQuote from './components/NewQuote.vue';
  import Header from './components/Header.vue';
  export default {
    data: function() {
      return {
        quotes: ['One quote just to see something'],
        maxQuotes: 10
      }
    },
    methods: {
      newQuote(quote) {
        if (this.quotes.length >= this.maxQuotes) {
          return alert("Maximum number of quotes reached. Please delete some quotes in order to add new ones!")
        }
        this.quotes.push(quote)
      },
      deleteQuote(index) {
        this.quotes.splice(index, 1)
      }
    },
    components: {
      appQuotesGrid: QuotesGrid,
      appNewQuote: NewQuote,
      appHeader: Header
    }
  }
</script>

<style>
</style>
