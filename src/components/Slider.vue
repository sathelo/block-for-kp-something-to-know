<template>
  <div class="content slider">
    <div class="slider__count">{{ current + 1 }}/{{ sliders.length }}</div>
    <div class="slider__controls controls">
      <button
        @click="backSlide"
        class="controls__btn controls__btn--left btn"
        :class="{
          'btn--hiden': current === 0,
        }"
      >
        <img src="/images/arrow-left-outline.svg" alt="slider-arrow-left" />
      </button>
      <img class="slider__image" :src="sliders[current].image" alt="image" />
      <button
        @click="nextSlide"
        class="controls__btn controls__btn--right btn"
        :class="{
          'btn--hiden': current === sliders.length - 1,
        }"
      >
        <img src="/images/arrow-right-outline.svg" alt="slider-arrow-right" />
      </button>
    </div>
    <p class="slider__text">
      {{ sliders[current].text }}
    </p>
    <button class="slider__btn btn">
      Искать промокод
      <img src="/images/arrow-right-long.svg" alt="arrow-right-long" />
    </button>
  </div>
</template>

<script>
export default {
  props: {
    sliders: Array,
  },

  data() {
    return {
      current: 0,
    };
  },
  methods: {
    backSlide() {
      this.current--;
    },

    nextSlide() {
      this.current++;
    },
  },
};
</script>

<style lang="scss" scoped>
.slider {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

  &__count {
    display: flex;
    align-items: center;
    justify-content: center;

    font-family: "KinopoiskBold";
    font-size: 15px;
    line-height: 56px;
    width: 56px;
    text-align: center;

    color: #000000;

    background: #ffffff;
    box-shadow: 0px 5px 26px rgba(0, 0, 0, 0.1);

    border-radius: 50%;

    margin-bottom: 105px;

    @media screen and (max-width: 900px) {
      max-width: 50px;
      height: 50px;

      margin-bottom: 60px;
    }
  }

  &__controls {
    margin-bottom: 64px;

    @media screen and (max-width: 900px) {
      margin-bottom: 50px;
    }
  }
  .controls {
    position: relative;
    display: flex;
    width: 100%;

    &__btn {
      z-index: 2;

      &--left {
        margin-right: auto;
      }

      &--right {
        margin-left: auto;
      }
    }
  }

  &__text {
    z-index: 2;

    font-family: "KinopoiskLite";
    font-size: 20px;
    line-height: 32px;

    text-align: center;
    letter-spacing: 0.4px;

    color: #000000;

    margin-bottom: 18.5px;

    @media screen and (max-width: 900px) {
      font-size: 16px;
      line-height: 28px;

      text-align: center;
      letter-spacing: 0.4px;

      margin-bottom: 18px;
    }
  }

  &__image {
    position: absolute;
    top: -195%;
    left: 50%;
    width: 30vw;
    min-width: 100px;
    max-width: 303.13px;
    transform: translate(-58%);

    @media screen and (max-width: 900px) {
      top: -90%;
      width: 24vw;
    }
  }

  &__btn {
    z-index: 2;

    display: flex;
    align-items: center;
    gap: 24px;

    background: #ffffff;
    border-radius: 8px;

    font-family: "KinopoiskReguar";
    font-size: 15px;
    line-height: 18px;
    text-align: center;

    color: #333333;

    padding: 19.33px 27.41px;
  }

  .btn.btn--hiden {
    pointer-events: none;
    opacity: 0;
  }
}
</style>
