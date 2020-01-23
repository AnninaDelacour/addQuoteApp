<template>
  <div class="container">
    <div class="row">
      <div class="col-12">
        <header>
          <h1>{{ header }}</h1>
          <div class="col-12">
            <Addbar :quoteCount="quotes.length" :maxQuotes="maxQuotes"></Addbar>
          </div>
        </header>
      </div>

      
      <div class="col-12 d-flex justify-content-center">
        <Quotefield @quoteAdded="newQuote"></Quotefield>
      </div>


      
        <div class="col-12 text-center mb-5 mt-3">
          <div class="alert-info"><small>Info: Click on quote to delete it</small></div>
        </div>
      
      

      <div class="col-12">
        <Quotegrid :quotes="quotes" @quoteDeleted="deleteQuote"></Quotegrid>
      </div>

    </div>
  </div>
</template>

<script>
import Addbar from "./components/Addbar";
import Quotefield from "./components/Quotefield";
import Quotegrid from "./components/Quotegrid";

export default {
  name: "app",
  props: ["addQuote"],
  data() {
    return {
      header: "Quotes Added",
      quotes: ["“Twenty years from now you will be more disappointed by the things that you didn’t do than by the ones you did do.”"],
      maxQuotes: 10
    };
  },
  methods: { //add new quote-boxes (see: quotefield!)
    newQuote(quote) {
      if (this.quotes.length >= this.maxQuotes) {
        return alert('Please delete Quotes before adding a new one!');
      }
      this.quotes.push(quote);
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1); //removes 1 element from the quotes'-array'
    }
  },
  components: {
    Addbar,
    Quotefield,
    Quotegrid
  }
};
</script>

<style lang="scss">
body {
  padding: 2rem;
}


.addBtn {
  margin: 1rem;
}
</style>
