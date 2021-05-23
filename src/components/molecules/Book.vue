<template>
  <div :class="$style.bookContent">
    <div :class="$style.image">
      <img
        :src="bookImage"
        alt=""
        @click="onGiveInfo(), $router.push('/book')"
      />
    </div>
    <div :class="$style.read" @click="onGiveInfo(), $router.push('/book')">
      читать описание
    </div>
    <div :class="$style.price">{{ bookPrice }} $</div>
    <div :class="$style.add">добавить в карзину</div>
  </div>
</template>

<script>
import { mapMutations } from "vuex";
export default {
  props: {
		bookName: String,
    bookId: String,
    bookImage: String,
    bookPrice: Number,
  },
  methods: {
    ...mapMutations(["getChosenBook"]),
    onGiveInfo() {
      this.getChosenBook(this.bookName);
    },
  },
};
</script>


<style lang="scss" module>
.bookContent {
  background-color: #ffffff;
  box-shadow: 0px 16px 24px rgba(0, 0, 0, 0.06), 0px 2px 6px rgba(0, 0, 0, 0.04),
    0px 0px 1px rgba(0, 0, 0, 0.04);
  border-radius: 16px;
  padding: 20px;
	height: 100%;
  .image {
    max-width: 100%;
    margin: 0 0 10px 0;
		cursor: pointer;
		border-radius: 8px;
		overflow: hidden;
    img {
      width: 100%;
      height: 100%;
    }
  }
	.read{
		margin: 0 0 10px 0;
		font-size: 17px;
		cursor: pointer;
	}
	.price{
		margin: 0 0 7px 0;
		font-size: 16px;
		color: #439a86;
	}
}
</style>