<template>
  <div class="card">
    <div class="card__item"
         v-for="card in cards"
         :key="card.mission"
    >
      <img
          class="card__item-img"
          :src="require(`@/assets/img/${card.image}`)"
          :alt="card.title"
      >
      <div class="card__item-info">
        <div class="card__item-info-mission">
          {{ card.mission }}
        </div>
        <h2 class="card__item-info-title">
          {{ card.title }}
        </h2>
        <p class="card__item-info-text">
          {{ card.text }}
        </p>
        <div class="card__item-info-data">
          <div class="card__item-info-data-wrapper">
            <img
                src="@/static/img/calendar.svg"
                alt="calendar"
                class="card__item-info-data-wrapper-img"
            >
            <span class="card__item-info-data-wrapper-text">
              {{ card.data.fullData }}
            </span>
          </div>
          <div class="card__item-info-data-wrapper">
            <img
                src="@/static/img/clock.svg"
                alt="time"
                class="card__item-info-data-wrapper-img"
            >
            <span class="card__item-info-data-wrapper-text">
              {{ card.data.time }}
            </span>
          </div>
          <div class="card__item-info-data-wrapper">
            <img
                src="@/static/img/rocket.svg"
                alt="rocket"
                class="card__item-info-data-wrapper-img"
            >
            <span class="card__item-info-data-wrapper-text">
              {{ card.rocket }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    cards: {
      type: Array,
      default: () => [],
    }
  }
}
</script>

<style lang="scss">
@import '../assets/scss/_variables';
@import '../assets/scss/_mixins';

.card__item {
  background: rgba(34, 36, 43, 0.8);
  margin-top: 20px;
  display: grid;
  grid-template-columns: 25% 75%;
  padding: 50px;
  &:first-child {
    margin-top: 0;
  };
  &-img {
    display: block;
    margin: 0 auto;
    max-width: 90%;
  }
  &-info {
    &-mission {
      color: $colorBlue;
      font-weight: 400;
      letter-spacing: 7px;
    }
    &-title {
      font-size: 72px;
      margin: 10px 0;
    }
    &-text {
      font-family: "Ubuntu",serif;
      font-size: 18px;
      line-height: 140%;
    }
    &-data {
      margin-top: 20px;
      display: flex;
      &-wrapper {
        display: flex;
        align-items: center;
        &-img {
          margin-left: 7px;
        }
        &-text {
          margin-left: 5px;
          font-size: 24px;
          line-height: 100%;
          letter-spacing: 2px;
        }
      }
    }
  }
}

@include mobile {
  .card__item {
    grid-template-columns: 100% 0;
    padding: 20px;
    &-img {
      display: none;
    }
    &-info {
      &-title {
        font-size: 72px;
        line-height: 100%;
        margin: 16px 0 20px;
      }
      &-data {
        flex-flow: column wrap;
        &-wrapper {
          margin-bottom: 20px;
          &-text {
            margin-left: 11px;
          }
        }
      }
    }
  }
}
</style>