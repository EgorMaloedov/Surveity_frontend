<template>
  <div v-if="loading" class="loader"></div>
  <slot v-else/>
</template>

<script setup>
import { useTestsStore } from "../../stores/testsStore.js";
import { computed } from "vue";

const testsStore = useTestsStore();
const loading = computed(() => testsStore.isLoading);
</script>

<style scoped>
.loader {
  width: 10rem;
  height: 10rem;
  border: 5rem solid transparent;
  border-top: 2px solid white;
  border-radius: 50%;
  animation: spin 1s linear infinite;
  margin: 0 auto;
}

@keyframes spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
</style>
