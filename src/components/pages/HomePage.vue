<template>
  <div :class="$style.page">
    <Header headerText="LAST BOOK" />
    <nav :class="$style.authorMenu">
      <li
        v-for="author in getAuthors"
        :key="author.id"
        @click="$router.push('/books')"
      >
        <AuthorMenuItem :authorName="author.name" :authorId="author.id" />
      </li>
    </nav>
  </div>
</template>

<script>
import { mapGetters } from "vuex";
import Header from "../molecules/Header";
import AuthorMenuItem from "../atoms/AuthorMenuItem";
export default {
  computed: mapGetters(["getAuthors", "getChosenAuthor"]),
  components: {
    Header,
    AuthorMenuItem,
  },
};
</script>

<style lang="scss" module>
.page {
  max-width: 1540px;
  margin: 0 auto;
  .authorMenu {
    display: flex;
		padding: 15px 0;
    margin: 0 0 50px 0;
		list-style-type: none;
		border-bottom: 2px solid #000;
    li {
      margin: 0 15px;
      font-size: 30px;
    }
  }
  .book {
    font-size: 20px;
  }
}
</style>