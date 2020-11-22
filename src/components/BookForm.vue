<template>
  <form v-on:submit.prevent="bookSubmit(bookData)" class="" action="#" method="post">
    <input v-model="bookData.bookTitle" type="text" name="title" value="" placeholder="Book Title">
    <input v-model="bookData.bookAuthor" type="text" name="author" value="" placeholder="Book Author">
    <div>
      <label for="finishedReading">Finished Reading</label>
      <input type="checkbox" v-model="bookData.finishedReading" name="finishedReading">
    </div>
    <div>
      <label for="borrowed">Borrowed</label>
      <input type="radio" v-model="bookData.ownership" name="borrowed" value="borrowed">

      <label for="bought">Bought</label>
      <input type="radio" v-model="bookData.ownership" name="bought" value="bought">
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
    bookSubmit(bookData) {
      this.$emit("addBook", bookData);
    }
  }
};
</script>

<style>
</style>
