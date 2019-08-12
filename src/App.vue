<template>
  <div class="container">
    <app-new-quote @addQuote="newQuote"></app-new-quote>
    <app-quotes-grid :quotes="quotes"></app-quotes-grid>
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
  export default {
    data: function() {
      return {
        quotes: ['One quote just to see something'],
        maxQuotes: 10
      }
    },
    methods: {
      newQuote(quote) {
        this.quotes.push(quote)
      }
    },
    components: {
      appQuotesGrid: QuotesGrid,
      appNewQuote: NewQuote
    }
  }
</script>

<style>
</style>
