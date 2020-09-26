<template>
  <form class="form">
    <div class="form__row">
      <input class="form__input" type="text" placeholder="Название компании" v-model="company">
      <input class="form__input" type="text" placeholder="Email" v-model="email">
      <input class="form__input" type="number" placeholder="Телефон" v-model="number">
    </div>
    <input class="form__button" type="button" value="Попробовать бесплатно"
      @click="handleClick">
  </form>
</template>

<script>
export default {
  data () {
    return {
      company: '',
      email: '',
      number: '380'
    }
  },
  methods: {
    handleClick () {
      let error = false
      if (this.company === '' || this.email === '' || this.number === '') {
        error = true
      }

      this.company = this.stringEdit(this.company)
      this.email = this.stringEdit(this.email)
      this.number = this.stringEdit(this.number)

      const atpos = this.email.indexOf('@')

      if (atpos !== this.email.length - 1) {
        const dotpos = this.email.slice(atpos + 1).indexOf('.')
        if (dotpos > 0) {
          if (dotpos === this.email.slice(atpos + 1).length - 1) {
            error = true
          }
        } else {
          error = true
        }
      } else {
        error = true
      }

      if (this.number.toString(2).length !== 12 && this.number.toString(2).length !== 10) {
        error = true
      }

      if (error) {
        alert('Input correct data')
      } else {
        alert(`company is ${this.company} email is ${this.email} number is ${this.number}`)
        this.company = ''
        this.email = ''
        this.number = 380
      }
    },
    stringEdit (string) {
      return string.replace(/\s+/g, ' ')
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
