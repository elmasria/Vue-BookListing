<template>
  <form v-on:submit.prevent="bookSubmit(bookTitle, bookAuthor)" class="" action="#" method="post">
    <input type="text" v-model="bookTitle" name="title" value="" placeholder="Book Title">
    <input type="text" v-model="bookAuthor"  name="author" value="" placeholder="Book Author">
    <button type="submit" name="button">Add Book</button>
  </form>
</template>

<script>
export default {
  name: 'BookForm',
  props: ['books'],
  data() {
    return {
      bookTitle: '',
      bookAuthor: '',
    };
  },
  methods: {
    bookSubmit: function(bookTitle, bookAuthor) {
      this.$emit('addBook', bookTitle, bookAuthor);
    }
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
