<template>
  <form v-on:submit.prevent="bookSubmit(bookData)" class="" action="#" method="post">
    <input v-model="bookData.bookTitle" type="text" name="title" value="" placeholder="Book Title" />
    <input v-model="bookData.bookAuthor" type="text" name="author" value="" placeholder="Book Author" />
    <div>
      <label for="finishedReading">
        Finished Reading
        <input v-model="bookData.finishedReading" type="checkbox" name="finished reading" id="finishedReading" />
      </label>
    </div>
    <label for="borrowed">
      <input v-model="bookData.ownership" type="radio" name="borrowed" id="borrowed" />
      borrowed
    </label>
    <label for="bought">
      <input v-model="bookData.ownership" type="radio" name="bought" id="bought"/>
      bought
    </label>

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
