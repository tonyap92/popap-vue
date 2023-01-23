<script setup>
import { ref } from 'vue';
import AppPopap from '@/components/AppPopap.vue';

const isInfoPopapVisible = ref(false);

const onTogglePopapInfo = () => {
  isInfoPopapVisible.value = !isInfoPopapVisible.value;
  console.log('> StartView -> onTogglePopapInfo', isInfoPopapVisible.value);
};

onTogglePopapInfo();
</script>

<template>
  <div class="max-w-xl mx-auto text-center">
    <AppPopap
      @onClosePopap="onTogglePopapInfo"
      :isInfoPopapVisible="isInfoPopapVisible"
      class="w-20 fixed top-3 r-0 l-0"
    />
    <button @click="onTogglePopapInfo" class="py-2 px-4 border border-solid border-black">Open</button>
  </div>
</template>

<style scoped></style>
