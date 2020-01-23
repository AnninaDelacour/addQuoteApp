<template>
  <div>
    <b-col sm="10">
      <b-form-textarea
        id="textarea"
        placeholder="Type in your favourite quote"
       rows="3" v-model="quote"></b-form-textarea>
    </b-col>
    <div class="col-12">
        <b-button class="addBtn mx-auto d-flex" variant="danger" @click.prevent="addQuote">Add Quote</b-button>
      </div>
  </div>
</template>

<script>
export default {
  name: "Quotefield",
  data() {
    return {
      quote: ''
    }
  },
  methods: {
    addQuote() {
      this.$emit('quoteAdded', this.quote);
      this.quote = '';
    }
  }
};
</script>

<style lang="scss" scoped>
#textarea {
  height: 100px;
  width: 800px;
  margin-top: 5rem;
}
</style>
