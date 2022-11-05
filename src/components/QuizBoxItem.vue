<template lang="pug">
.quiz-box-item(:class="[{ 'animate-pulse': isFlicker }, `quiz-box-item-${id}`]")
  .quiz-box-item__ball(v-if="hasBall") {{id}}
</template>

<script lang="ts">
import { computed, defineComponent } from "vue"

export default defineComponent({
  name: "QuizBoxItem",
  props: {
    id: {
      type: Number,
      required: true
    },
    hasBall: {
      type: Boolean,
      default: false
    },
    isFlicker: {
      type: Boolean,
      default: false
    },
  },
  setup(props) {
    return {}
  },
})
</script>
<style lang="scss" scoped>

@keyframes panning {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(500px);
  }
}

.quiz-box-item {
  @apply flex justify-center items-center;
  @apply border-2 border-black;
  background: radial-gradient(circle, rgba(113,81,95,1) 81%, rgba(0,0,0,1) 100%);
  &__ball {
    width: 30px;
    height: 30px;
    background-color: #A5F12B;
    animation: panning 5s linear infinite;
    @apply rounded-full flex justify-center items-center text-black;
  }
}
</style>