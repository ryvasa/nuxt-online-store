<template>
  <div
    class="pt-24 flex flex-col justify-start items-start lg:flex-row gap-8 pb-8 px-4 lg:px-8"
  >
    <div class="flex-1 flex flex-col gap-4">
      <div class="carousel w-full">
        <div class="carousel-item relative w-full max-h-3/4">
          <NuxtImg
            class="w-full object-contain rounded-md"
            :src="currentImage.url"
          />
          <div
            class="absolute left-5 right-5 top-1/2 flex -translate-y-1/2 transform justify-between"
          >
            <button
              @click="handleClickRight"
              href="#slide3"
              class="btn btn-circle btn-ghost"
            >
              ❮
            </button>
            <button
              @click="handleClickLeft"
              href="#slide1"
              class="btn btn-circle btn-ghost"
            >
              ❯
            </button>
          </div>
        </div>
      </div>
      <div class="flex justify-between border-b-2 border-gray-700 p-2 lg:p-4">
        <p class="text-xl text-primary font-semibold">$10000000</p>
        <button class="btn btn-primary btn-sm">Add to cart</button>
      </div>
    </div>
    <div class="flex-1 flex gap-4 flex-col">
      <h1 class="text-2xl font-bold text-primary">Product Name</h1>
      <div class="flex flex-col gap-2">
        <h2 class="text-xl font-semibold text-primary">Description</h2>
        <p class="">
          Lporro est nesciunt impedit quas nam animi reprehenderit saepe quae a
          quos exercitationem iure. Repellendus deserunt nobis maxime, iure nam
          tempora? Consequatur, porro nostrum accusantium iste explicabo quia,
          facere debitis aspernatur incidunt et architecto animi assumenda
          minima voluptatum consectetur, asperiores aliquid? Quos et dicta
          dolore praesentium eligendi aliquam facilis enim.
        </p>
      </div>
      <div class="flex flex-col gap-1">
        <h2 class="text-xl font-semibold text-primary">Specification</h2>
        <div class="flex">
          <div class="flex-1">
            <div class="flex flex-col gap-2">
              <div class="flex justify-between items-center py-2">
                <p class="text-sm">Weight</p>
                <p class="text-primary font-semibold text-sm">10g</p>
              </div>
            </div>
            <div class="flex flex-col gap-2">
              <div class="flex justify-between items-center py-2">
                <p class="text-sm">Height</p>
                <p class="text-primary font-semibold text-sm">10cm</p>
              </div>
            </div>
            <div class="flex flex-col gap-2">
              <div class="flex justify-between items-center py-2">
                <p class="text-sm">Width</p>
                <p class="text-primary font-semibold text-sm">10cm</p>
              </div>
            </div>
            <div class="flex flex-col gap-2">
              <div class="flex justify-between items-center py-2">
                <p class="text-sm">Weight</p>
                <p class="text-primary font-semibold text-sm">10g</p>
              </div>
            </div>
          </div>
          <div class="flex-1"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
const currentImage = ref({
  id: 1,
  url: 'background/mobilebg.jpg',
});
const images = [
  {
    id: 1,
    url: '/background/mobilebg.jpg',
  },
  {
    id: 2,
    url: '/background/mobilejas.jpg',
  },
  {
    id: 3,
    url: '/background/mobileman.jpg',
  },
  {
    id: 4,
    url: '/background/mobileshoes.jpg',
  },
];
const handleClickRight = () => {
  if (currentImage.value.id >= images.length) {
    currentImage.value = images[0];
  } else {
    currentImage.value = images[currentImage.value.id];
  }
};

const handleClickLeft = () => {
  if (currentImage.value.id <= images[0].id) {
    currentImage.value = images[images.length - 1];
  } else {
    currentImage.value = images[currentImage.value.id - 2];
  }
};
</script>

<style></style>
