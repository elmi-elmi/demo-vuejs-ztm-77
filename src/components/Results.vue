<template>
  <div class="result">
    <div class="title">{{ results[index].title }}</div>
    <div class="desc">
      {{ results[index].desc }}
    </div>
  </div>
</template>

<script>
export default {
  props: ['totalCorrect', 'results'],
  computed: {
    index() {
      let index = 0;
      this.results.forEach((result, idx) => {
        if (
          this.totalCorrect >= result.min &&
          this.totalCorrect <= result.max
        ) {
          index = idx;
        }
      });
      return index;
    },
  },
};
</script>

<style></style>
