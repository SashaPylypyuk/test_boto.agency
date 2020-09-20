<template>
  <div id="app">
    <div class="left">
      <p class="left__text--title text__black">
        Попробуйте БЕСПЛАТНО
      </p>
      <div class="left__row">
        <div class="row__left">
          <p class="row__left--number text__black">
            2000
          </p>
          <p class="row__left--businesses text__black">
            БИЗНЕСОВ
          </p>
        </div>
        <div class="row__right">
          <strong class="row__right--text text__black">
            уже попробовали JoinChat
          </strong>
          <p class="row__right--text-small">
            Присоединяйтесь к ним - создайте аккаунт прямо сейчас. Первые 15 дней бесплатно.
          </p>
        </div>
      </div>
      <Form />

    </div>
    <Right />
  </div>
</template>

<script>
import Right from './components/Right.vue'
import Form from './components/Form.vue'

export default {
  name: 'App',
  components: {
    Right,
    Form
  }
}
</script>

<style lang="scss">
html, body {
  height: 100%;
}
@font-face {
  font-family: "Gotham Pro";
  src: url("fonts/Gotham Pro/GothamPro.woff");
}
@font-face {
  font-family: "Gotham Pro Black";
  src: url("fonts/Gotham Pro/GothamPro-Black.ttf");
}

* {
  font-family: Gotham Pro, sans-serif;
  margin: 0;
  padding: 0;
}
  #app {
    width: 100%;
    height: 100%;
    display: flex;
  }
  .left {
    max-width: 1980px;
    width: 61%;
    background-color: #FDDE00;
    padding: 150px 100px 0 100px;

    &__text--title {
      font-size: 55px;
      margin-bottom: 20px;
      letter-spacing: -0.05em;
    }

    &__row {
      display: flex;
      margin-bottom: 50px;
    }
  }
  .row {
    &__left {
      margin-right: 30px;
      position: relative;

      &::after {
        content: "";
        position: absolute;
        display: block;
        width: 7px;
        height: 95px;
        top: 0;
        right: -15px;
        background-color: #000;
      }
    }
    &__left--number {
      font-size: 60px;
      margin-bottom: -5px;
    }
    &__left--businesses {
      font-size: 30px;
    }

    &__right--text {
      font-size: 25px;
      &-small {
        margin-top: 15px;
        font-size: 15px;
      }
    }
  }

  .text__black {
    font-family: "Gotham Pro Black", sans-serif;
  }
  @media (min-width: 2000px) {
    .left {
      padding: 10%;
    }

    .image__iphone {
      left: -10%;
    }

  }
  @media (max-width: 1025px) {
    .left {
      padding: 15% 6% 15% 2%;
    }
    .image__iphone {
    width: 200px;
    height: 413px;
    top: -3%;
    left: -25%;
    }

    .image__ipad {
      margin: 150px 0 0 10px;
    }

    .form {
      width: 100%;
      align-items: center;
      align-content: center;
      &__row {
        flex-direction: column;
        margin-bottom: 20px;
      }
      &__input {
        width: 90%;
        margin: 0 auto 10px auto;
      }
      &__button {
        width: 100%;
      }
    }
  }

  @media (max-width: 769px) {
    .image__iphone {
      left: -30%;
    }
  }

  @media (max-width: 426px) {
    .left {
      padding: 15% 1%;
      width: 100%;
      text-align: center;

      &__text--title {
        font-size: 48px;
      }

      &__row {
        flex-wrap: wrap;
      }
    }

    .row {
      &__left {
        width: 100%;
        &--number, &--businesses {
          width: 80%;
          margin: 0 auto;
        }
        &::after {
          display: none;
        }
      }
    }
    .right {
      display: none;
    }
  }
</style>
