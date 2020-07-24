<template>
  <form v-on:submit.prevent="bookSubmit(bookTitle, bookAuthor)" class="" action="#" method="post">
    <input v-model="bookTitle" type="text" name="title" value="" placeholder="Book Title">
    <input v-model="bookAuthor" type="text" name="author" value="" placeholder="Book Author">
    
    <div>
      <label for="finishedReading">
        Finished Reading
      <input v-model=.../bookData.finishedReading type="checkbox">
      </label>
    </div>
    <div>
      <label for="borrowed">
        borrowed
      <input v-model=".../bookData.ownership" value="borrowed" type="radio">
      </label>
      <label for="bought">
        bought
      <input v-model=".../bookData.ownership" value="bought" type="radio">
      </label>
    </div>
    <button type="submit" name="button">Add Book</button>
  </form>
</template>

<script>
export default {
  name: "BookForm",
  props: ["books"],
  data() {
    return {
      bookData: {
        bookTitle: "",
        bookAuthor: "",
        finishedReading: false,
        ownership: []
      }
    };
  },
  methods: {
    bookSubmit(bookTitle, bookAuthor) {
      this.$emit("addBook", bookTitle, bookAuthor);
    }
  }
};
</script>

<style>
</style>
