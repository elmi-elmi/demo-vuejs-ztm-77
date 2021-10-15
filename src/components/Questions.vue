<template>
  <div class="questions-ctr">
    <div class="progress">
      <div class="bar"></div>
      <div class="status">
        {{ +questionNumber + 1 }} out of 3 questions answered
      </div>
    </div>
    <div
      class="single-question"
      v-for="(question, indx) in questions"
      :key="question.q"
      v-show="indx == questionNumber"
    >
      <div class="question">
        {{ question.q }}
      </div>
      <div
        class="answers"
        v-for="answer in question.answers"
        :key="answer.text"
      >
        <div class="answer" @click="selectedAnswer(answer.is_correct)">
          {{ answer.text }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['questions', 'questionNumber'],
  emits: ['selected-answer'],
  methods: {
    selectedAnswer(is_correct) {
      this.$emit('selected-answer', is_correct);
    },
  },
};
</script>

<style></style>
