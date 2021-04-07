<template>
  <div class="app">
    <header class="header">
      <img class="header__logo" src="@/assets/img/spacex.svg" alt="logo">
      <h1 class="header__title">
        Space <span class="header__title_white">X</span>
        <span class="header__title_newline">Missions</span>
      </h1>
    </header>
    <section class="flight-list">
      <card :cards="data"/>
    </section>
  </div>
</template>

<script>
import Card from './components/Card.vue'

import main from '@/mock/main.json';

export default {
  name: 'App',
  components: {
    Card,
  },
  data() {
    return {
      data: Object.freeze(main.cards),
    }
  }
}
</script>

<style lang="scss">
@import './assets/scss/main';

@include mobile {
  .header {
    height: auto;

    &__title {
      font-weight: 300;
      font-size: 120px;
      line-height: 90%;
    }
  }
}
</style>