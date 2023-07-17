<script setup lang="ts">
import Elias from '../assets/Emne-min.png'
import Beat from '../assets/808.mp3'
import { ref } from 'vue'

const count = ref(0)
const clicked = ref(false)

const audio = new Audio(Beat)

const clickOnElias = () => {
  count.value = count.value + 1
  clicked.value = true
  setTimeout(() => clicked.value = false, 1000)
  audio.load()
  audio.play()
}

</script>

<template>
  <div class="bg-gray-800 w-screen h-screen relative">
    <img @click="clickOnElias" :class="clicked ? 'animate-spin' : ''" class="w-full h-full" :src="Elias" alt="Her har du Elias Tafjord">
    <p class="text-white absolute top-1/4 sm:top-2/4 left-6 sm:left-10 lg:left20 text-xl sm:text-2xl md:text-3xl lg:text-6xl font-bold">Trykk: {{ count && count + '👏' }}</p>
  </div>
</template>
