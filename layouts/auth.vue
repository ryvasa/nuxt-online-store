<template>
  <div class="relative">
    <NuxtImg
      class="h-screen w-screen object-cover fixed -z-10 hidden lg:block"
      src="bg.jpg"
      alt="background"
    />
    <div class="fixed h-full w-3/5 lg:flex justify-end hidden">
      <div class="flex fixed top-20 flex-col pr-36 justify-center items-center">
        <h1 class="text-4xl font-bold text-gray-700">
          <span class="text-primary">Online</span> Store
        </h1>
        <p class="text-gray-700">
          Lorem ipsum dolor <span class="text-primary">sit amet.</span>
        </p>
      </div>
    </div>
    <slot />
  </div>
</template>

<script setup></script>

<style></style>
