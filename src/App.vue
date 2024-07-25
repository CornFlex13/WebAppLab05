<script setup>
import { onMounted } from 'vue';
import { useTableStore } from './store/table';
import { useQueueStore } from './store/queue';
const tableStore = useTableStore();
onMounted(async () => {
  await tableStore.fetchTables();
});
const queueStore = useQueueStore();
onMounted(async () => {
  await queueStore.fetchQueues();
});
</script>

<template>
  <VApp>
    <RouterView />
  </VApp>
</template>
