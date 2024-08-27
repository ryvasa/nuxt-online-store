<template>
  <div class="relative lg:pt-0 pt-16">
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
  </div>
</template>

<script setup lang="ts">
const currentImage = ref({
  id: 1,
  url: 'background/editedbg.jpg',
});
const images = [
  {
    id: 1,
    url: '/background/editedbg.jpg',
  },
  {
    id: 2,
    url: '/background/editedjas.jpg',
  },
  {
    id: 3,
    url: '/background/editedman.jpg',
  },
  {
    id: 4,
    url: '/background/editedshoes.jpg',
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
onMounted(() => {
  const interval = setInterval(() => {
    handleClickRight();
  }, 3000); // Ganti gambar setiap 3 detik

  // Bersihkan interval saat komponen di-unmount
  onUnmounted(() => {
    clearInterval(interval);
  });
});
</script>

<style></style>
