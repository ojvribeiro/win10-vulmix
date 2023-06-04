<template>
  <ToolbarSystemButton
    @mouseover="taskViewState = '2'"
    @mouseout="taskViewState = '1'"
  >
    <Icon
      v-for="i in 2"
      :name="`task-view-${i}`"
      :class="[
        taskViewState === i.toString() ? 'opacity-100' : 'opacity-0',

        `item-${i}`,
      ]"
    />
  </ToolbarSystemButton>
</template>

<script setup lang="ts">
  const taskViewState = ref<string>('1')
</script>

<style scoped>
  .item-1 {
    transform: translateX(50%);
  }
  .item-2 {
    transform: translateX(-50%);
  }
</style>
