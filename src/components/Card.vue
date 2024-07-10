<template>
  <div :class="bordered ? 'bordered' : ''" class="container">
    <div class="percents" :class="percentsColor ? percentsColor : ''">{{ percents }}
      <img src="@/assets/arrow-up.svg" v-if="percentsColor === 'green'" />
      <img src="@/assets/arrow-down.svg" v-if="percentsColor === 'red'" />
    </div>
    <p :class="textColor ? textColor : ''">{{ text }}</p>
  </div>
</template>

<script setup>
import { defineProps } from "vue";

const props = defineProps({
  percents: String,
  text: String,
  bordered: Boolean,
  percentsColor: { type: String, required: false },
  textColor: { type: String, required: false }
})
</script>

<style scoped>
.container {
  padding: 20px 24px 24px 16px;
  width: 220px;
}

.bordered {
  border: 1px solid var(--border-lgrey);
  margin: 24px 5px 24px 0;
}

.percents {
  font-size: 30px;
  font-weight: bolder;
}

.blue {
  color: var(--text-lblue);
}

.green {
  color: var(--text-green);
}

.red {
  color: var(--text-red);
}

.white {
  color: var(--text-white);
}
</style>