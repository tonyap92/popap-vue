<script setup>
const props = defineProps(['isInfoPopapVisible']);
const emit = defineEmits(['onClosePopap']);

const onClosePopap = () => {
  emit('onClosePopap');
};

onClosePopap();
</script>

<template>
  <div v-show="isInfoPopapVisible" class="p-4 bg-white">
    <div
      class="max-w-screen-xl max-h-full fixed top-50 left-0 right-0 z-10 w-full mx-auto p-8 pb-4 bg-white"
      style="height: calc(100% - 3.5rem)"
    >
      <div class="w-full flex justify-between items-center">
        <span>Popap Name</span>

        <button @click="onClosePopap">
          <span class="flex uppercase gap-2">
            <i class="material-icons">close</i>
          </span>
        </button>
      </div>

      <div class="flex content-center items-center">
        <slot></slot>
      </div>

      <div class="flex justify-between items-center"></div>
    </div>

    <div class="fixed top-0 left-0 right-0 z-0 max-w-595 w-full mx-auto h-full bg-gray-700 bg-opacity-60"></div>
  </div>
</template>

<style scoped></style>
