<template>
  <div class="assento">
    <slot />
  </div>
</template>

<script setup lang="ts"></script>

<style scoped>
.assento {
  width: 100px;
  height: 100px;
  background-color: red;
  border-radius: 100%;
}
</style>
