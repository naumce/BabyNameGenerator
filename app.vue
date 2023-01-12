<template>
  <div class="flex place-content-center">
    <div class="font-sans w-2/3 text-center text-cyan-700">
      <h1 class="text-xl font-bold py-5">Baby Name Generator</h1>

      <p class="py-5">
        Choose your options and click the "Find Names" button below
      </p>
      <div class="bg-pink-300 rounded-3xl">
        <div class="options-container">
          <h4 class="font-bold text-lg py-4">1- Choose a gender</h4>
          <div class="option-buttons">
            <button
              class="bg-gray-300 hover:bg-gray-400 text-gray-800 font-bold py-1 px-4 inline-flex items-center border-2 border-pink-400 rounded-tl-2xl rounded-bl-2xl"
            >
              Boy
            </button>
            <button
              class="bg-gray-300 hover:bg-gray-400 text-gray-800 font-bold py-1 px-4 inline-flex items-center border-2 border-pink-400 border-l-0 border-r-0"
            >
              Unisex
            </button>
            <button
              class="bg-gray-300 hover:bg-gray-400 text-gray-800 font-bold py-1 px-4 items center inline-flex border-2 border-pink-400 rounded-tr-2xl rounded-br-2xl"
            >
              Girl
            </button>
          </div>
        </div>
        <div class="options-container">
          <h4 class="font-bold text-lg py-4">
            2- Choose the name's popularity
          </h4>
          <div class="option-buttons">
            <button
              class="bg-gray-300 hover:bg-gray-400 text-gray-800 font-bold py-1 px-4 items-center inline-flex border-2 border-r-0 border-pink-400 rounded-tl-2xl rounded-bl-2xl"
            >
              Unique
            </button>
            <button
              class="bg-gray-300 hover:bg-gray-400 text-gray-800 font-bold py-1 px-4 items-center inline-flex border-2 border-pink-400 rounded-tr-2xl rounded-br-2xl"
            >
              Trendy
            </button>
          </div>
        </div>
        <div class="options-container">
          <h4 class="font-bold text-lg py-4">3- Choose the name's length</h4>
          <div class="option-buttons pb-5">
            <button
              class="bg-gray-300 hover:bg-gray-400 text-gray-800 font-bold py-1 px-4 inline-flex items-center border-2 border-r-0 border-pink-400 rounded-tl-2xl rounded-bl-2xl"
            >
              Long
            </button>
            <button
              class="bg-gray-300 hover:bg-gray-400 text-gray-800 font-bold py-1 px-4 inline-flex items-center border-2 border-pink-400"
            >
              All
            </button>
            <button
              class="bg-gray-300 hover:bg-gray-400 text-gray-800 font-bold py-1 px-4 inline-flex items-center border-2 border-l-0 border-pink-400 rounded-tr-2xl rounded-br-2xl"
            >
              Short
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
