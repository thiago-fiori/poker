<template>
  <div>
    <div class="mesa">
      <slot />
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped>
.mesa {
  width: 600px;
  height: 600px;
  background-color: green;
  margin: auto;
}
</style>
