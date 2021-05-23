<template>
  <div :class="$style.popularBooks">
    <div :class="$style.content">
      <div :class="$style.book" v-for="book in getPopularBooks" :key="book.id">
        {{ book.name }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    getPopularBooks: Array,
  },
};
</script>

<style lang="scss" module>
.popularBooks{
	.content{
		display: flex;
		margin: 0 -15px;
		.book{
			padding: 0 15px;
			flex: 0 1 33.333%;
			text-align: center;
		}
	}
}
</style>