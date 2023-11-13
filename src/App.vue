<template>
  <div class="min-h-screen bg-gray-100 flex items-center justify-center">
    <div class="bg-white p-8 flex flex-col space-y-4 rounded-xl shadow-md w-96">
      <input
        placeholder="Zip Code"
        @input="onZipCodeChange"
        class="w-full p-2 border rounded-md focus:outline-none focus:ring focus:ring-blue-200 transition"
      />
      <input
        placeholder="City"
        :value="city"
        class="w-full p-2 border rounded-md focus:outline-none focus:ring focus:ring-blue-200 transition"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import { useDebounceFn } from '@vueuse/core';
import { ref } from 'vue';

interface GetCityByZipCodeResponse {
  zips: [
    {
      id: number,
      country_id: number,
      zip: string,
      name: string,
      lat: number,
      lng: number,
      country: {
        id: number,
        name: string
      }
    }
  ]
}

let city = ref('');

function onZipCodeChange(event: InputEvent) {
  const inputValue = (event.target as HTMLInputElement).value;

  if (inputValue) {
    fetchCity(inputValue);
  }
}

const fetchCity = useDebounceFn(async (zipCode: string) => {
  try {
    const response = await fetch(`https://testa.free.beeceptor.com/zips/${zipCode}.json`);
    const citiesResponse: GetCityByZipCodeResponse = await response.json();

    if (citiesResponse?.zips?.length) {
      city.value = citiesResponse.zips[0].name;
    }
  } catch (error) {
    console.error(error);
  }
}, 300)
</script>
