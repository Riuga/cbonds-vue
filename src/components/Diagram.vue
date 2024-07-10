<template>
  <div class="diagram">
    <b>{{ data }}</b>
    <div class="rect" :class="clr" :style="{ height: Math.floor(data) + 'px' }"></div>
  </div>
</template>

<script setup>
import { defineProps } from 'vue'

const props = defineProps({
  data: String,
  clr: String
})
</script>

<style scoped>
.diagram {
  align-self: flex-end;
}
.rect {
  width: 60px;
  border-top: 3px solid;
  margin-top: 10px;
  margin-right: 16px;
  margin-bottom: 8px;
}

.blue {
  background-color: var(--chart-blue);
  border-color: var(--border-blue);
}

.orange {
  background-color: var(--chart-orange);
  border-color: var(--border-orange);
}
</style>