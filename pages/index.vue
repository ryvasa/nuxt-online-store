<template>
  <div class="flex flex-col gap-2 lg:gap-4">
    <Carousel />
    <div class="px-8 py-4 lg:hidden">
      <label class="input input-bordered flex items-center gap-2">
        <input type="text" class="grow" placeholder="Search" />
        <svg
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 16 16"
          fill="currentColor"
          class="h-4 w-4 opacity-70"
        >
          <path
            fill-rule="evenodd"
            d="M9.965 11.026a5 5 0 1 1 1.06-1.06l2.755 2.754a.75.75 0 1 1-1.06 1.06l-2.755-2.754ZM10.5 7a3.5 3.5 0 1 1-7 0 3.5 3.5 0 0 1 7 0Z"
            clip-rule="evenodd"
          />
        </svg>
      </label>
    </div>
    <div class="flex gap-4 flex-col w-full justify-center items-center">
      <BestSellerProducts />
      <NewProducts />
      <CategorySection />
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style></style>
