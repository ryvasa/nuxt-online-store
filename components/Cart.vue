<template>
  <div class="drawer drawer-end z-20">
    <input id="cart" type="checkbox" class="drawer-toggle" />

    <div class="drawer-side">
      <label
        for="cart"
        aria-label="close sidebar"
        class="drawer-overlay"
      ></label>
      <ul class="menu bg-base-200 text-base-content min-h-full w-2/5 p-4">
        <!-- Sidebar content here -->
        <li><a>Sidebar Item 1</a></li>
        <li><a>Sidebar Item 2</a></li>
      </ul>
    </div>
  </div>
</template>

<script setup></script>

<style></style>
