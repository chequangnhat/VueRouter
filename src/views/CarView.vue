<script setup>
import { useRoute } from "vue-router";
import { ref, watch,  onBeforeMount, onMounted } from "vue";
import cars from "../data.json";

const route = useRoute();
const car = ref(null);
const { id } = route.params;

onBeforeMount(() => {
  car.value = cars.find((c) => {
    return c.id == parseInt(id);
  });
  console.log("in before mount")
  console.log(car.value);

});

onMounted(() => {
  console.log("on mounted")
  console.log(car.value);
});
</script>

<template>
  <div>car view</div>
  <div>{{ car.make }}</div>
  <div>{{ car.price }}</div>
</template>
