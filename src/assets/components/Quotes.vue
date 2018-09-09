<template>
  <div class="row">
    <div class="col-sm-12 .bg-dark">
      <h2>All Quotes</h2>
    </div>
    <single-quote v-for="(quote,i) in quotes" @click.native="deleteQuote(i)">{{quote}}</single-quote>
  </div>  
</template>

<script>
import SingleQuote from "./SingleQuote.vue";
export default {
  props: ["quotes"],
  components: {
    SingleQuote
  },
  methods: {
    deleteQuote: function(i) {
      //  this.quotes.splice(i,1)
      this.$emit("quoteToDelete", i);
    }
  }
};
</script>
<style>
</style>


