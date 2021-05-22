<template>
	<span @click="ChangeAuthor">{{authorName}}</span>
</template>

<script>
import { mapMutations } from "vuex";
export default {
	props: {
		authorName: String,
		authorId: Number
	},
	methods: {
	...mapMutations(["changeAuthor"]),
	ChangeAuthor() {
		this.changeAuthor(this.authorId)
	}
}
}
</script>

<style lang="scss" module>

</style>