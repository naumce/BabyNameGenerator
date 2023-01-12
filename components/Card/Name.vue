<template>
  <div
    class="bg-blue-900 w-40 py-2 text-red-100 rounded-xl my-4 border-blue-900 relative mx-1"
  >
    <h4>{{ name }}</h4>
    <p
      class="absolute cursor-pointer bg-black -top-1/4 left-3/4 w-14 bg-transparent pt-2 rounded-full p-0 m-0"
      @click="removeName(name)"
    >
      x
    </p>
  </div>
</template>

<script setup lang="ts">
interface NameProps {
  name: string
}

const props = defineProps<NameProps>()
const emit = defineEmits(["remove"])

const removeName = () => {
  emit("remove", props.index)
}
</script>
