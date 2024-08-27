<template>
  <div class="drawer drawer-end z-20">
    <input id="notification" type="checkbox" class="drawer-toggle" />

    <div class="drawer-side">
      <label
        for="notification"
        aria-label="close sidebar"
        class="drawer-overlay"
      ></label>
      <div
        class="menu relative bg-base-200 text-base-content min-h-full w-11/12 lg:w-2/5 p-4"
      >
        <label for="notification" class="cursor-pointer absolute top-5">
          <svg
            class="text-error w-6 h-6"
            xmlns="http://www.w3.org/2000/svg"
            width="32"
            height="32"
            viewBox="0 0 24 24"
          >
            <path
              fill="currentColor"
              d="M12 2C6.47 2 2 6.47 2 12s4.47 10 10 10s10-4.47 10-10S17.53 2 12 2m5 13.59L15.59 17L12 13.41L8.41 17L7 15.59L10.59 12L7 8.41L8.41 7L12 10.59L15.59 7L17 8.41L13.41 12z"
            />
          </svg>
        </label>
        <ul class="relative top-6 lg:top-8">
          <li><a>Sidebar Item 1</a></li>
          <li><a>Sidebar Item 2</a></li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style></style>
