<template>
  <div :class="$style.page">
    <Header :headerText="getChosenBook.name" />
    <div :class="$style.book">
      <div :class="$style.bookImage">
        <img :src="getChosenBook.image" alt="" />
      </div>
      <div :class="$style.description">
        {{ getChosenBook.bookDes }}
      </div>
    </div>
  </div>
</template>

<script>
import { mapGetters } from "vuex";
import Header from "../molecules/Header";
export default {
  computed: mapGetters(["getChosenBook"]),
  components: {
    Header,
  },
};
</script>

<style lang="scss" module>
.page {
  max-width: 1540px;
  margin: 0 auto;
	min-height: 100vh;
	background: #f1f1f1;
  .book {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    .bookImage {
      max-width: 300px;
      max-height: 500px;
      img {
        width: 100%;
        height: 100%;
      }
    }
  }
}
</style>