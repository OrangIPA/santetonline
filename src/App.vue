<script setup lang="ts">
import { ref } from "vue";
import bg from "./assets/image.png";

const nama = ref("");
const isHover = ref(false);

function mulaiSantet() {
  isHover.value = true;
}
</script>

<template>
  <div
    class="w-screen flex flex-col items-center py-2 h-screen"
    :style="`background-image: url(${bg})`"
  >
    <div class="text-4xl bg-red-200 p-3">Santet Online</div>

    <div class="mt-28 bg-red-200 p-3">Masukkan nama:</div>
    <div class="bg-red-200 p-3">
      <input v-model="nama" type="text" class="border border-black px-0.5" />
    </div>
    <button
      @click="mulaiSantet"
      class="mt-2 border px-1 bg-red-400 hover:bg-red-600 cursor-pointer"
    >
      Mulai Santet!
    </button>
  </div>

  <div
    v-if="isHover"
    class="absolute inset-0 grid place-items-center w-screen h-screen bg-black/20"
    @click="
      () => {
        isHover = false;
        nama = '';
      }
    "
  >
    <div class="p-3 bg-red-200">Selamat! {{ nama }} berhasil disantet</div>
  </div>
</template>
