<template>
  <div :class="$style.authorDescription">
    <div :class="$style.text">{{authorDescription}}</div>
  </div>
</template>

<script>
export default {
  props: {
    authorDescription: String,
  },
};
</script>

<style lang="scss" module>
.authorDescription{
	max-width: 1200px;
	margin: 0 auto;
}
</style>