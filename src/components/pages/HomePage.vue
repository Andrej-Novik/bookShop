<template>
  <div :class="$style.page">
    <Header
      headerText="LAST BOOK"
      :isBurher="true"
      :getIsBurgerOpen="getIsBurgerOpen"
    />
    <nav :class="$style.authorMenu">
      <li
        v-for="author in getAuthors"
        :key="author.id"
        @click="$router.push('/books')"
      >
        <AuthorMenuItem :authorName="author.name" :authorId="author.id" />
      </li>
    </nav>
    <div :class="$style.content">
      <HomePageDescription />
    </div>
		<div :class="$style.line"></div>
    <div :class="$style.content">
      <PopularBooks :getPopularBooks="getPopularBooks" />
    </div>
		<div :class="$style.line"></div>
		<div :class="$style.content">
      цитаты
    </div>
		<div :class="$style.pictures">
			<div :class="$style.picture">
				<img src="../../assets/images/homePage2.jpg" alt="">
			</div>
			<div :class="$style.picture">
				<img src="../../assets/images/homePage1.jpg" alt="">
			</div>
		</div>
  </div>
</template>

<script>
import { mapGetters } from "vuex";
import Header from "../molecules/Header";
import AuthorMenuItem from "../atoms/AuthorMenuItem";
import PopularBooks from "../organisms/PopularBooks";
import HomePageDescription from "../molecules/HomePageDescription";
export default {
  computed: mapGetters([
    "getAuthors",
    "getChosenAuthor",
    "getIsBurgerOpen",
    "getPopularBooks",
  ]),
  components: {
    Header,
    AuthorMenuItem,
    PopularBooks,
    HomePageDescription,
  },
};
</script>

<style lang="scss" module>
.page {
  max-width: 1540px;
  margin: 0 auto;
  min-height: 100vh;
  background-color: #f1f1f1;
  .authorMenu {
    display: flex;
    padding: 15px 0;
    list-style-type: none;
    border-bottom: 2px solid #000;
    li {
      margin: 0 15px;
      font-size: 20px;
    }
  }
  .book {
    font-size: 20px;
  }
  .content {
    max-width: 1200px;
    margin: 0 auto;
  }
	.line{
		border-bottom: 2px solid #000;
		margin: 25px 0;
	}
	.pictures{
		display: flex;
		height: 200px;
		.picture{
			flex: 1 1 50%;
			height: 200px;
			img{
				width: 100%;
				height: 100%;
			}
		}
	}
}
</style>