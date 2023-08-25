<template>
  <main class="home">
    <div class="home__cloud home__cloud--top"></div>
    <div class="home__cloud home__cloud--left"></div>
    <div class="home__cloud home__cloud--left-back"></div>
    <div class="home__cloud home__cloud--center"></div>
    <div class="home__cloud home__cloud--right"></div>
    <div class="home__cloud home__cloud--right-back"></div>
    <div class="home__left">
      <SideMenu :menu="menu" />
      <a @click.prevent href="#">
        <img src="/images/arrow-top-long.svg" alt="arrow-bottom-long" />
        <span>Скрольте вниз</span>
      </a>
    </div>
    <div class="home__content content">
      <img class="home__logo" src="/images/logo.svg" alt="logo" />
      <h1 class="home__title">ОНИ ДОЛЖНЫ ЧТО-ТО ЗНАТЬ</h1>
      <Slider :sliders="sliders" />
    </div>
    <div class="home__right">
      <a @click.prevent href="hd.kinopoisk.ru">hd.kinopoisk.ru</a>
    </div>
  </main>
</template>

<script>
import Slider from "./components/Slider.vue";
import SideMenu from "./components/SideMenu.vue";

export default {
  data() {
    return {
      sliders: [
        {
          image: "./images/image.png",
          text: "1Для примера мы показали вам его лицо. В первой серии он прячется в подвале за мониторами, и пусть борода не собьёт вас с толку. Найдите героя и нажмите  на паузу — ему не терпится отдать вам промокод.",
        },
        {
          image: "./images/image.png",
          text: "2Для примера мы показали вам его лицо. В первой серии он прячется в подвале за мониторами, и пусть борода не собьёт вас с толку. Найдите героя и нажмите  на паузу — ему не терпится отдать вам промокод.",
        },
        {
          image: "./images/image.png",
          text: "3Для примера мы показали вам его лицо. В первой серии он прячется в подвале за мониторами, и пусть борода не собьёт вас с толку. Найдите героя и нажмите  на паузу — ему не терпится отдать вам промокод.",
        },
        {
          image: "./images/image.png",
          text: "4Для примера мы показали вам его лицо. В первой серии он прячется в подвале за мониторами, и пусть борода не собьёт вас с толку. Найдите героя и нажмите  на паузу — ему не терпится отдать вам промокод.",
        },
        {
          image: "./images/image.png",
          text: "5Для примера мы показали вам его лицо. В первой серии он прячется в подвале за мониторами, и пусть борода не собьёт вас с толку. Найдите героя и нажмите  на паузу — ему не терпится отдать вам промокод.",
        },
        {
          image: "./images/image.png",
          text: "6Для примера мы показали вам его лицо. В первой серии он прячется в подвале за мониторами, и пусть борода не собьёт вас с толку. Найдите героя и нажмите  на паузу — ему не терпится отдать вам промокод.",
        },
        {
          image: "./images/image.png",
          text: "7Для примера мы показали вам его лицо. В первой серии он прячется в подвале за мониторами, и пусть борода не собьёт вас с толку. Найдите героя и нажмите  на паузу — ему не терпится отдать вам промокод.",
        },
        {
          image: "./images/image.png",
          text: "8Для примера мы показали вам его лицо. В первой серии он прячется в подвале за мониторами, и пусть борода не собьёт вас с толку. Найдите героя и нажмите  на паузу — ему не терпится отдать вам промокод.",
        },
      ],
      menu: [
        {
          text: "",
          active: false,
        },
        {
          text: "",
          active: false,
        },
        {
          text: "Подсказки",
          active: true,
        },
        {
          text: "",
          active: false,
        },
      ],
    };
  },
  components: {
    Slider,
    SideMenu,
  },
};
</script>

<style lang="scss" scoped>
.home {
  position: relative;
  display: flex;
  align-items: stretch;
  justify-content: space-between;

  background-image: url(/images/sky.svg);
  background-size: cover;
  background-repeat: no-repeat;

  width: 100vw;
  height: 100vh;

  padding: 21px 29px 27px 28px;

  &__content {
    display: flex;
    align-items: center;
    flex-direction: column;

    .content {
      width: 100%;
      max-width: 902px;
    }

    @media screen and (max-width: 900px) {
      max-width: 570px;
    }
  }

  &__logo {
    z-index: 2;

    margin-bottom: 25px;

    @media screen and (max-width: 900px) {
      max-height: 22px;

      margin-bottom: 12px;
    }
  }

  &__title {
    z-index: 2;

    font-family: "FuturaBold";
    font-style: normal;
    font-weight: 700;
    font-size: 45px;
    line-height: 72px;

    text-align: center;
    letter-spacing: 0.003px;
    text-transform: uppercase;

    color: #ffcc64;

    margin-bottom: 32px;

    @media screen and (max-width: 900px) {
      font-size: 32px;
      line-height: 55px;

      margin-bottom: 8px;
    }
  }

  &__left {
    z-index: 2;

    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: space-between;

    a {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 25px;
      font-family: "KinopoiskReguar";
      font-size: 14px;
      line-height: 15px;

      transform: rotate(180deg);

      img {
        max-width: 63px;
      }

      span {
        writing-mode: vertical-rl;
        text-orientation: mixed;
      }
    }
  }

  &__right {
    z-index: 2;

    text-align: center;

    writing-mode: vertical-rl;
    text-orientation: mixed;

    font-family: "KinopoiskReguar";
    font-size: 14px;
    line-height: 15px;

    text-align: center;

    color: #333333;
  }

  &__cloud {
    z-index: 1;

    position: absolute;

    width: 100%;
    height: 100%;

    top: 0px;
    right: 0px;
    bottom: 0px;
    left: 0px;

    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;

    &--top {
      top: -75px;

      background-image: url(/images/clouds/cloudTop.png);
    }

    &--left {
      background-image: url(/images/clouds/cloudLeft.png);

      &-back {
        background-image: url(/images/clouds/cloudRight.png);
      }
    }

    &--center {
      background-image: url(/images/clouds/cloudCenter.png);
    }

    &--right {
      background-image: url(/images/clouds/cloudRight.png);

      &-back {
        background-image: url(/images/clouds/cloudRight.png);
      }
    }
  }

  @media screen and (max-height: 500px) {
    height: 100%;
  }
}
</style>
