<template>
  <div class="main-page">
  <h1>{{ msg }}</h1>
  <form @submit.prevent="result">
    <div class="field">
    <select @change="result" v-model="selected">
      <option disabled selected>{{selected}}</option>
      <option v-for="(option, index) in options" v-bind:value="option" :key="index">
        {{ option }}
      </option>
    </select>
    </div>
  </form>
  </div>
</template>

<script>
export default {
  name: 'MainPage',
  data () {
    return {
      options: [
        'Закончились этикетки 80',
        'Закончились этикетки 115',
        'Закончились этикетки 125',
        'Закончились этикетки 150',
        'Закончились этикетки 180',
        'Закончились этикетки 230'
      ],
      selected: 'Problem',
      msg: 'Ok'
    }
  },
  methods: {
    result () {
      if (this.selected === 'Закончились этикетки 80') {
        this.msg = 'Перейти к изготовлению 115'
      } else if (this.selected === 'Закончились этикетки 115') {
        this.msg = 'Перейти к изготовлению 125'
      } else if (this.selected === 'Закончились этикетки 125') {
        this.msg = 'Перейти к изготовлению 150'
      } else if (this.selected === 'Закончились этикетки 150') {
        this.msg = 'Перейти к изготовлению 180'
      } else if (this.selected === 'Закончились этикетки 180') {
        this.msg = 'Перейти к изготовлению 230'
      } else if (this.selected === 'Закончились этикетки 230') {
        this.msg = 'Бери шинель...'
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.btn {
  margin-top: 20px;
}
</style>
