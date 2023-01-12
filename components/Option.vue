<template>
  <div class="options-container">
    <h4 class="font-bold text-lg py-4">{{ option.title }}</h4>
    <div class="option-buttons">
      <button
        v-for="(value, index) in option.buttons"
        :key="value"
        class="bg-green-200 hover:bg-pink-300 text-gray-800 font-bold py-1 px-4 inline-flex items-center border-2 border-pink-400"
        :class="computedButtonClasses(value, index)"
        @click="options[option.category] = value"
      >
        {{ value }}
      </button>
    </div>
  </div>
</template>

<script setup lang="ts">
import { Gender, Popularity, Length } from "@/data"

interface OptionProps {
  option: {
    title: string
    category: string
    buttons: Gender[] | Popularity[] | Length[]
  }
  options: {
    gender: Gender
    popularity: Popularity
    length: Length
  }
}

const computedButtonClasses = (value, index) => {
  const classNames = []
  if (props.options[props.option.category] === value) {
    classNames.push("bg-pink-400")
  }
  if (index === 0) {
    classNames.push("rounded-tl-2xl  rounded-bl-2xl")
  }
  if (index === props.option.buttons.length - 1) {
    classNames.push("rounded-tr-2xl  rounded-br-2xl")
  }

  return classNames.join(" ")
}
const props = defineProps<OptionProps>()
</script>
