<template>
  <div class="section">
    <h1>Росстат на Cbonds</h1>
    <p>Делегируйте вопрос написания качественных текстов опытным авторам: посты для соцсетей, SEO-оптимизированные
      статьи
      на сайт, продающие описания для карточки товаров. Закажите перевод или редактуру текстов.</p>
    <Categories />
    <h2>Цены, инфляция</h2>
  </div>
  <div class="section-blue">
    <div class="section">
      <h3>Индекс потребительской цены</h3>
      <div class="row">
        <Card v-for="card in consumerPrice.slice(0, Math.ceil(consumerPrice.length / 2))" v-bind="card" />
      </div>
      <hr>
      <div class="row">
        <Card v-for="card in consumerPrice.slice(Math.ceil(consumerPrice.length / 2), consumerPrice.length)"
          v-bind="card" />
      </div>
    </div>
  </div>
  <div class="section-grey">
    <div class="section">
      <h2>Инфляция в России</h2>
      <Chart v-bind="chart" />
    </div>
  </div>
  <div class="section">
    <h2>Топ 5 снижений/приростов цен по товарам и услугам за последний месяц</h2>
    <b>Стали дешевле</b>
    <div class="row">
      <Card v-for="card in becameCheaper" v-bind="card" />
    </div>
    <b>Стали дороже</b>
    <div class="row">
      <Card v-for="card in becameExpensive" v-bind="card" />
    </div>
  </div>
</template>

<script setup>
import Categories from "./components/Categories.vue"
import Card from "@/components/Card.vue"
import Chart from "@/components/Chart.vue"
import { consumerPrice, becameCheaper, becameExpensive } from "@/data/cards.js"
import { chart } from '@/data/chart.js'
</script>

<style scoped>
.section {
  width: 60%;
  margin: 0 auto;
  padding: 24px 0;
}

.section-blue {
  background-color: var(--bg-blue);
  color: var(--text-white);
}

.section-grey {
  background-color: var(--bg-lightgrey);
}

.row {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}

@media screen and (max-width: 1024px) {
  .section {
    width: 80%;
  }
}

@media screen and (max-width: 500px) {
  .section {
    width: 100%;
    padding: 2rem;
  }
}
</style>
