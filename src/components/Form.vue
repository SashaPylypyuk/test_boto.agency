<template>
  <form class="form">
    <div class="form__row">
      <input :class="{ error: isError }" class="form__input" type="text" placeholder="Название компании" v-model="company">
      <input :class="{ error: isError }" class="form__input" type="text" placeholder="Email" v-model="email">
      <input :class="{ error: isError }" class="form__input" type="number" placeholder="Телефон" v-model="number">
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
      number: '380',
      isError: false
    }
  },
  methods: {
    handleClick () {
      this.isError = false
      if (this.company === '' || this.email === '' || this.number === '') {
        this.isError = true
      }

      this.company = this.stringEdit(this.company)
      this.email = this.stringEdit(this.email)
      this.number = this.stringEdit(this.number)

      const atpos = this.email.indexOf('@')

      if (atpos !== this.email.length - 1) {
        const dotpos = this.email.slice(atpos + 1).indexOf('.')
        if (dotpos > 0) {
          if (dotpos === this.email.slice(atpos + 1).length - 1) {
            this.isError = true
          }
        } else {
          this.isError = true
        }
      } else {
        this.isError = true
      }

      if (this.number.toString(2).length !== 12 && this.number.toString(2).length !== 10) {
        this.isError = true
      }

      if (this.isError) {
        alert('Input correct data')
      } else {
        this.isError = false
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

    &:hover, &:focus {
      border: 1px solid #6FA9BB;
    }
  }

  &__row {
    display: flex;
    justify-content: space-between;
    margin-bottom: 50px;
  }

  &__button {
    outline: none;
    cursor: pointer;
    width: 331px;
    height: 55px;
    border: none;
    border-radius: 5px;
    color: #fff;
    background-color: #000;

    &:hover {
      animation: pulse 1s;
      box-shadow: 0 0 0 2em rgba(#000,0);
    }

  }
}

.error {
  border: 1px solid #ff0000;

  &:hover, &:focus {
    border: 1px solid #ff0000;
  }
}

@keyframes pulse {
  0% { box-shadow: 0 0 0 0 #000; }
}
</style>
