<template>
  <div class="row">
      <Quote v-for="(quote, index) in quotes" :key="quote" @click.native="deleteQuote(index)">{{ quote }}</Quote>
  </div>
</template>

<script>
import Quote from "./Quote";


export default {
    name: "Quotegrid",
    props:['quotes'],
    components: {
        Quote
    },
    methods: {
        deleteQuote(index) {
            this.$emit('quoteDeleted', index);
        }
    }
};
</script>

<style lang="scss" scoped>

</style>