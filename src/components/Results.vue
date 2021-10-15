<template>
  <div class="result">
    <div class="title">You got sample result {{ totalCorrect }}!</div>
    <div class="desc">
      Enter a short description here about the result.
    </div>
  </div>
  <button type="button" class="reset-btn">Reset</button>
</template>

<script>
export default {
  props: ['totalCorrect'],
};
</script>

<style></style>
