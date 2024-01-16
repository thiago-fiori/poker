<template>
  <div class="mesa">
    <slot />
  </div>
</template>

<script setup lang="ts"></script>

<style scoped>
.mesa {
  position: relative;
  width: 1200px;
  height: 600px;
  background-color: green;
  margin: auto;
  border-radius: 40%;
  padding: 0;
}
</style>
