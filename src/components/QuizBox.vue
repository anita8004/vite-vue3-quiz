<template lang="pug">
div(:class="['quiz-box', className]")
  .quiz-box__title {{title}}
  .quiz-box__content
    QuizBoxItem(
      v-for="num in 9"
      :key="num"
      :id="num"
      :hasBall="hasBall(num)"
      :isFlicker="isFlicker(num)"
    )
</template>

<script lang="ts">
import { defineComponent, PropType } from "vue";
import QuizBoxItem from "./QuizBoxItem.vue";

export default defineComponent({
  name: "QuizBox",
  components: {
    QuizBoxItem,
  },
  props: {
    title: {
      type: String,
      default: ""
    },
    className: {
      type: String,
      default: ""
    },
    hasBallArray: {
      type: Array as PropType<number[]>,
      default: () => [1,3,7,9]
    },
    isFlickerArray: {
      type: Array as PropType<number[]>,
      default: () => [3,5,9]
    },
  },
  setup(props) {

    const hasBall = (id: number) => props.hasBallArray.some((number) => number === id);

    const isFlicker = (id: number) => {
      return props.isFlickerArray.some((number) => number === id);
    }

    return {
      hasBall,
      isFlicker,
    }
  },
})
</script>
<style lang="scss" scoped>
.quiz-box {
  @apply mb-10;
  &__title {
    @apply text-3xl mb-4;
  }
  &__content {
    @apply grid overflow-hidden;
    grid-template-columns: repeat(3,200px);
    grid-template-rows: repeat(3,100px);
    gap: 16px;
    width: min-content;
  }
}
</style>