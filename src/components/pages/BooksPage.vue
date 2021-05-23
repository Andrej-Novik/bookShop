<template>
  <div :class="$style.page">
    <Header :headerText="getChosenAuthor.name" />
    <AuthorDescription :authorDescription="getChosenAuthor.authorDescription" />
    <div :class="$style.books">
      <div :class="$style.booksContent">
        <div
          :class="$style.book"
          v-for="book in getChosenAuthor.books"
          :key="book.id"
          :bookId="book.id"
         
        >
          <Book
            :bookName="book.name"
            :bookId="book.id"
            :bookImage="book.image"
            :bookPrice="book.price"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { mapGetters } from "vuex";
import Book from "../molecules/Book";
import Header from "../molecules/Header";
import AuthorDescription from "../molecules/AuthorDescription";
export default {
  computed: mapGetters(["getChosenAuthor"]),
  components: {
    Header,
    Book,
    AuthorDescription,
  },
};
</script>

<style lang="scss" module>
.page {
  max-width: 1540px;
  margin: 0 auto;
	min-height: 100vh;
  .books {
    max-width: 1200px;
    margin: 0 auto;
    .booksContent {
      display: flex;
      flex-wrap: wrap;
      margin: 0 -15px;
      .book {
        padding: 0 15px;
        text-align: center;
        flex: 0 1 20%;
        margin: 0 0 30px 0;
      }
    }
  }
}
</style>