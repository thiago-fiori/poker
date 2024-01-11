<template>
  <div class="container">
    <div class="mesa">
      <slot />
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped>
.mesa {
  width: 1200px;
  height: 600px;
  background-color: green;
  margin: auto;
  border-radius: 40%;
}
.container {
  width: 100%;
  height: 100dvh;
  display: flex;
}
</style>
