<template>
  <div class="container">
    <div class="chart row">
      <div class="periods">
        <p v-for="period in periods">
        <div class="dot" :class="period.clr"></div>
        {{ period.label }}
        </p>
      </div>

      <div class="labeled-diagrams" v-for="item in data">
        <div class="combined-diagrams row">
          <Diagram v-for="diagram in item.diagrams" v-bind="diagram" />
        </div>
        <b>{{ item.label }}</b>
      </div>
    </div>
  </div>
</template>

<script setup>
import { defineProps } from 'vue'
import Diagram from '@/components/Diagram.vue'

const props = defineProps({
  periods: [{ label: String, clr: String }],
  data: [{ label: String, diagrams: [{ data: String, clr: String }] }]
})
</script>

<style scoped>
.dot {
  width: 15px;
  height: 15px;
  border-radius: 7px;
  margin-right: 5px;
  display: inline-block;
  border: 3px solid;
}

.container {
  padding: 5px;
  align-content: flex-end;
}

.combined-diagrams {
  display: flex;
  flex-direction: row;
}

.labeled-diagrams {
  padding: 5px;
  align-content: flex-end;
}

.periods {
  padding: 5px;
  align-content: center;
}

.row {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}

.chart {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-between;
}

.blue {
  border-color: var(--border-blue);
}

.orange {
  border-color: var(--border-orange);
}

@media screen and (max-width: 1410px) {
  .periods {
    order: 1;
  }
}
</style>