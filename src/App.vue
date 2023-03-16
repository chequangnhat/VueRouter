<script setup>
import { RouterView, RouterLink } from "vue-router";
</script>

<template>
  <header class="">
    <RouterLink class="mr-5" to="/">home</RouterLink>
    <RouterLink to="/about">about</RouterLink>
  </header>
  <div
    class="h-screen w-screen mx-auto flex flex-col justify-center items-center"
  >
    <RouterView />
  </div>
</template>

<style scoped></style>
