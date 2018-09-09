<template>
    <div class="container">
        <my-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></my-header>
        <new-quote @newQuote="addQuote"></new-quote>
        <my-quotes :quotes="quotes" @quoteToDelete="deleteAquote">{{quotes}}</my-quotes>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert alert-success" 
    :class="{red: activeRed}">Info: {{info}}</div>
            </div>
        </div>
    </div>
</template>

<script>
import Quotes from "./assets/components/Quotes.vue";
import NewQuote from "./assets/components/NewQuote.vue";
import Header from "./assets/components/Header.vue";
export default {
  data: function() {
    return {
      quotes: ["Be yourself; everyone else is already taken." ],
      maxQuotes: 12,
      info: "Click on a Quote to delete it!",
      activeRed: false
    };
  },
  components: {
    MyQuotes: Quotes,
    NewQuote,
    MyHeader: Header
  },
  methods: {
    addQuote: function(quote) {
      if (quote.length == 0) {
        this.info = "Please, add some text for the quote!";
        this.activeRed=true;
        return;
      }
      if (this.quotes.length >= this.maxQuotes) {
        this.info = "Please, delete a quote before adding another!";
        this.activeRed=true;
        return;
      }
      this.quotes.push(quote);
      this.activeRed=false;
    },
    deleteAquote: function(i) {
      this.quotes.splice(i, 1);
    }
  }
};
</script>

<style>
.red {
  color: red;
}
</style>
