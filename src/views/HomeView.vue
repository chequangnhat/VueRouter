<script setup>
import { ref } from "vue";
import { useRouter } from "vue-router";
import carsData from "../data.json";

const router = useRouter()
const cars = ref(carsData);

const directToCarView = (id) => {
  router.push(`/car/${id}`)
}
</script>

<template>
  <div class="text-5xl font-semibold">Our cars</div>
  <div class="cards flex justify-center items-center flex-wrap">
    <div
      class="card h-[100px] w-[100px] flex flex-col justify-center items-center shadow-xl m-3 cursor-pointer p-3"
      v-for="car in cars"
      @click="directToCarView(car.id)"
    >
      <div>{{ car.make }}</div>
      <div>${{ car.price }}</div>
    </div>
  </div>
</template>
