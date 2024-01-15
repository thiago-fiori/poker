<template>
  <div>
    <h3 :style="{ color: `red` }">
      <slot></slot>
    </h3>
    <div class="assento"></div>
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
