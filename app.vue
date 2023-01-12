<template>
  <div class="flex place-content-center">
    <div class="font-sans w-2/3 text-center text-cyan-700">
      <h1 class="text-xl font-bold py-5">Baby Name Generator</h1>

      <p class="py-5">
        Choose your options and click the "Find Names" button below
      </p>
      <div class="options-container bg-pink-300 rounded-3xl">
        <Option
          v-for="option in optionsArray"
          :key="option.title"
          :option="option"
          :options="options"
        />
        <button
          class="bg-blue-400 hover:bg-blue-600 text-gray-300 font-bold py-1 px-6 inline-flex border-2 border-blue-800 rounded-2xl my-4 active:bg-blue-500"
          @click="computeSelectedNames"
        >
          Find Name
        </button>
      </div>
      <div class="cards flex mt-3 flex-wrap justify-around">
        <CardName
          v-for="(name, index) in selectedNames"
          :key="name"
          :name="name"
          @remove="() => removeName(index)"
          :index="index"
        />
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { Gender, Popularity, Length, OptionState, names } from "@/data.ts"

const options = reactive<OptionsState>({
  gender: Gender.GIRL,
  popularity: Popularity.TRENDY,
  length: Length.SHORT
})

const selectedNames = ref<string[]>([])

const optionsArray = [
  {
    title: "1 Choose a gender",
    category: "gender",
    buttons: [Gender.GIRL, Gender.BOY, Gender.UNISEX]
  },
  {
    title: "1 Choose  the name's popularity",
    category: "popularity",
    buttons: [Popularity.UNIQUE, Popularity.TRENDY]
  },
  {
    title: "1 Choose name's length",
    category: "length",
    buttons: [Length.SHORT, Length.ALL, Length.LONG]
  }
]
const computeSelectedNames = () => {
  const filteredNames = names
    .filter(name => name.gender === options.gender)
    .filter(name => name.popularity === options.popularity)
    .filter(name => {
      if (options.length === Length.ALL) return true
      else return name.length === options.length
    })
  selectedNames.value = filteredNames.map(name => name.name)
}
const removeName = (index: number) => {
  const filteredNames = [...selectedNames.value]
  filteredNames.splice(index, 1)
  selectedNames.value = filteredNames
}
</script>
<style scoped></style>
