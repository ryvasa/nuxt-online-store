<template>
  <div
    className="group rounded-md shadow-xl relative flex justify-center items-center overflow-hidden"
  >
    <figure>
      <NuxtImg
        src="category/122.jpg"
        alt="Shoes"
        class="lg:h-72 object-cover"
      />
    </figure>
    <div
      className="absolute h-full z-10 w-full justify-center items-center hidden group-hover:card-body hover:bg-black/50 hover:backdrop-blur-md "
    >
      <h2 className="card-title text-primary">Shoes</h2>
      <div className="card-actions justify-end">
        <button className="btn btn-primary">Buy Now</button>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style></style>
