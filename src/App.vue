<script setup lang="ts">

import { computed, ref } from 'vue';


const text = ref("");
const qrUrl = computed(() =>
  `https://quickchart.io/qr?text=${encodeURIComponent(text.value)}`
);

</script>

<template>
  <header>
  </header>
  <div class="w-full h-screen">
    <div class="mx-auto lg:w-2/10 w-8/10 mt-[100px]">
      <div class="text-center my-4 text-[20px]">
        QR GENERATOR
      </div>
      <div class="p-4 rounded-lg border-2 border-purple-500 shadow-lg">
        <input type="text" v-model="text" class="bg-gray-100 p-2 border-2 border-purple-500 rounded-lg w-full mb-2" placeholder="Enter Text">
        <br>
        <div class="mx-auto">
          <div  v-if="text !== ''" >
            <img :src="qrUrl" alt="QR Code" class="mx-auto w-full rounded-lg border-2 border-purple-500">
          </div>
          <div v-else class="text-center mt-4">
            No QR Generate
          </div>
        </div>
      </div>
    </div>
  </div>
  <div>

  </div>
</template>

<style scoped>

</style>
