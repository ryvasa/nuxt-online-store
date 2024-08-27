<template>
  <div
    class="flex flex-col gap-4 lg:gap-8 justify-center items-center py-2 lg:py-8"
  >
    <h1 class="text-3xl font-bold text-primary">Category Products</h1>
    <div class="lg:px-8 px-4 gap-4 lg:gap-8 grid grid-cols-2 lg:grid-cols-5">
      <CategoryCard />
      <CategoryCard />
      <CategoryCard />
      <CategoryCard />
      <CategoryCard />
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style></style>
