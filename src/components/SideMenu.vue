<template>
  <div class="sideMenu">
    <button
      @click="show ? (show = false) : (show = true)"
      class="sideMenu__burger btn"
    >
      <img src="/images/burger.svg" alt="burger" />
    </button>

    <div v-if="show" class="sideMenu__nav nav">
      <a @click.prevent v-for="(item, index) in menu" :key="index" href="#">
        <div class="nav__form" :class="item.active ? 'nav__form--active' : ''">
          <div v-if="item.text" class="nav__block">
            <div v-if="index < 10" class="nav__index">0{{ index + 1 }}</div>
            <div v-else class="nav__index">
              {{ index + 1 }}
            </div>
            <div class="nav__title">{{ item.text }}</div>
          </div>
          <span
            class="nav__form--line"
            :class="item.active ? 'nav__form--line-active' : ''"
          ></span>
        </div>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    menu: Array,
  },
  data() {
    return {
      show: true,
    };
  },
};
</script>

<style lang="scss" scoped>
.sideMenu {
  display: flex;
  justify-content: space-between;
  flex-direction: column;

  padding: 17px 6px;

  &__burger {
    margin-right: auto;

    margin-bottom: 157px;

    @media screen and (max-width: 900px) {
      margin-bottom: 25px;
    }
  }

  &__nav {
    position: relative;
    display: flex;
    flex-direction: column;
    gap: 53px;

    .nav {
      a {
        position: relative;
      }

      &__form {
        position: absolute;
        display: flex;
        flex-direction: column;

        &--active {
          top: 12.2vh;
          .nav__title {
            font-weight: bold;
          }

          @media screen and (max-width: 900px) {
            top: 17vh;
          }
        }

        &--line {
          cursor: auto;
          display: block;
          content: "";
          border: 1px solid rgba(51, 51, 51, 0.5);
          background: rgba(51, 51, 51, 0.5);
          width: 8px;
          transition: width 0.5s ease-out;
        }

        &--line-active {
          width: 100%;
        }
      }

      &__block {
        display: flex;
        align-items: flex-end;
        gap: 26px;

        margin-bottom: 6.57px;
      }

      &__index {
        font-family: "KinopoiskMedium";
        font-size: 16px;
        line-height: 15px;

        color: #2e332a;
      }

      &__title {
        font-family: "KinopoiskLight";
        font-size: 14px;
        line-height: 15px;

        color: #333333;
      }
    }
  }
}
</style>
