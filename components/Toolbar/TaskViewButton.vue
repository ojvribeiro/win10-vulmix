<template>
  <ToolbarSystemButton
    @mouseover="taskViewState = '2'"
    @mouseout="taskViewState = '1'"
  >
    <Icon :name="`task-view-${taskViewState}`" />
  </ToolbarSystemButton>
</template>

<script setup>
  const taskViewState = ref('1')
</script>
