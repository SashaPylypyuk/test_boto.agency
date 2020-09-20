<template>
  <form class="form">
    <div class="form__row">
      <input class="form__input" type="text" placeholder="Название компании" v-model="company">
      <input class="form__input" type="text" placeholder="Email" v-model="email">
      <input class="form__input" type="number" placeholder="Телефон" v-model="number">
    </div>
    <input class="form__button" type="submit" value="Попробовать бесплатно"
      @click="handleClick">
  </form>
</template>

<script>
export default {
  data () {
    return {
      company: '',
      email: '',
      number: ''
    }
  },
  methods: {
    handleClick () {
      alert(`company is ${this.company} email is ${this.email} number is ${this.number}`)
    }
  }
}
</script>

<style lang="scss">
.form {
  &__input {
    padding-left: 10px;
    width: 200px;
    height: 55px;
    border: none;
    border-radius: 5px;
    outline: none;
  }

  &__row {
    display: flex;
    justify-content: space-between;
    margin-bottom: 50px;
  }

  &__button {
    width: 331px;
    height: 55px;
    border: none;
    border-radius: 5px;
    color: #fff;
    background-color: #000;
  }
}
</style>
