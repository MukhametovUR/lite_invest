<!-- components/StockTable.vue -->
<template>
  <div class="container mx-auto p-8">
    <div class="overflow-x-auto bg-[#FBFBFB] rounded-lg p-6">
      <h1 class="text-4xl mb-5">Акции</h1>

      <div class="bg-white p-5 rounded-3xl shadow-sm">
        <table class="min-w-full table-auto" w-tid="16">
          <thead>
            <tr class="opacity-50">
              <th class="px-4 py-2 text-left font-light">Инструмент</th>
              <th class="px-4 py-2 text-left font-light">Обновление</th>
              <th class="px-4 py-2 text-left font-light">Позиция</th>
              <th class="px-4 py-2 text-left font-light">Комиссия (₽)</th>
              <th class="px-4 py-2 text-left font-light">Фин.рез (₽)</th>
              <th class="px-4 py-2 text-left font-light">Просадка (₽)</th>
              <th class="px-4 py-2 text-left font-light">Плечо</th>
            </tr>
          </thead>
          <tbody class="bg-[#FBFBFB] rounded-2xl" w-tid="26">
            <tr v-for="stock in stocks" :key="stock.name" w-tid="27">
              <td class="px-4 py-2 whitespace-nowrap">{{ stock.name }}</td>
              <td class="px-4 py-2 whitespace-nowrap">{{ stock.updated }}</td>
              <td class="px-4 py-2 whitespace-nowrap">{{ stock.position }}</td>
              <td class="px-4 py-2 whitespace-nowrap">{{ stock.commission }}</td>
              <td class="px-4 py-2 whitespace-nowrap" :style="`color:${stock.color}`">{{ stock.financial }}</td>
              <td class="px-4 py-2 whitespace-nowrap">{{ stock.additive }}</td>
              <td class="px-4 py-2 whitespace-nowrap">{{ stock.leverage }}</td>
            </tr>
          </tbody>
        </table>
        <p class="flex justify-center font-light py-2 mt-4 rounded-xl bg-[#FBFBFB]">
          <span class="opacity-50">Комиссия:</span><span class="px-1 mr-2">334,43 ₽</span><span class="mr-2">•</span>
          <span class="opacity-50">Фин. результат:</span> 76 354,82 ₽
        </p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const stocks = ref([
  { name: 'GAZP', updated: '20:20:28  24-06-24', position: '644', commission: '0', financial: '426 216,4 ', additive: '-6 000 000', leverage: 10, color: '#2DCE82' },
  { name: 'SBER', updated: '20:20:28  24-06-24', position: '532', commission: '334,43', financial: '360 232,68', additive: '-6 000 000', leverage: 10, color: '#F24F71' },
  { name: 'TATNP', updated: '20:20:28  24-06-24', position: '32915', commission: '0', financial: '10 371,1', additive: '-6 000 000', leverage: 10, color: '#2DCE82' },
])
</script>

 <style src="../assets/css/tailwind.css"></style>