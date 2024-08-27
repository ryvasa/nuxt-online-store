<template>
  <div class="rounded-md card-compact bg-base-200 overflow-hidden">
    <figure>
      <NuxtImg
        loading="lazy"
        src="background/shoes.jpg"
        alt="Shoes"
        class="h-72 object-cover"
      />
    </figure>
    <div class="card-body">
      <h2 class="card-title text-xl">Shoes</h2>
      <div class="card-actions justify-between items-center">
        <p class="text-primary text-lg">$100000</p>
        <button class="btn btn-primary btn-sm">Buy Now</button>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style></style>
