<template>
  <div
    class="flex flex-col gap-4 lg:gap-8 justify-center items-center py-2 lg:py-8"
  >
    <h1 class="text-3xl font-bold text-primary">New Products</h1>
    <div class="lg:px-8 px-4 gap-2 lg:gap-4 grid grid-cols-2 lg:grid-cols-5">
      <ProductCard />
      <ProductCard />
      <ProductCard />
      <ProductCard />
      <ProductCard />
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style></style>
