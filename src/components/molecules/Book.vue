<template>
  <div :class="$style.bookContent" @click="onGiveInfo">{{ bookName }}</div>
</template>

<script>
import { mapMutations } from "vuex";
export default {
  props: {
    bookName: String,
    bookId: String,
  },
  methods: {
    ...mapMutations(["getChosenBook"]),
    onGiveInfo() {
      this.getChosenBook(this.bookId);
    },
  },
};
</script>


<style lang="scss" module>
.bookContent {
  background: red;
}
</style>