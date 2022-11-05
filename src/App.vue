<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import QuizBox from "./components/QuizBox.vue";
</script>

<template lang="pug">
div.quiz-wrapper
  QuizBox(
    title="Quiz 1"
    className="quiz1"
  )
  QuizBox(
    title="Quiz 2"
    className="quiz2"
  )
  QuizBox(
    title="Quiz 3"
    className="quiz3"
  )
</template>

<style scoped lang="scss">
.quiz-wrapper {
  @apply p-10;
}

:deep(.quiz2) {
  .quiz-box-item__ball {
    @apply relative z-20;
  }
}

@keyframes panningToRB {
  0% {}
  100% {
    right: 0;
    bottom: 0;
  }
}

:deep(.quiz3) {
  .quiz-box__content {
    @apply relative;
  }

  .quiz-box-item {}
  .quiz-box-item__ball {
    @apply absolute z-20 animate-none;
    animation: panningToRB 2s ease-in-out infinite;
  }

  .quiz-box-item-1 .quiz-box-item__ball {
    right: calc(432px + 100px - 15px);
    bottom: calc(232px + 50px - 15px);
  }
  .quiz-box-item-3 .quiz-box-item__ball {
    right: calc(100px - 15px);
    bottom: calc(232px + 50px - 15px);
  }
  .quiz-box-item-7 .quiz-box-item__ball {
    right: calc(432px + 100px - 15px);
    bottom: calc(50px - 15px);
  }
  .quiz-box-item-9 .quiz-box-item__ball {
    right: calc(100px - 15px);
    bottom: calc(50px - 15px);
  }
}

</style>
