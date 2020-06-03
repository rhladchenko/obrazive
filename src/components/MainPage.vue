<template>
  <div class="main-page">
  <h1>{{ msg }}</h1>
  <form @submit.prevent="result">
    <div class="field">
    <select @change="result" name="press80" v-model="selected">
      <option disabled selected>{{selected}}</option>
      <option v-for="(option, index) in pres80.options" v-bind:value="option" :key="index">
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
      pres80: {
        options: [
          'Закончились этикетки 115_2',
          'Закончились этикетки 125_2',
          'Закончились этикетки 125_6'
        ]
      },
      msg: 'Ok',
      selected: 'Problem'
    }
  },
  methods: {
    result () {
      if (this.selected === 'Закончились этикетки 115_2') {
        this.msg = 'Перейти к изготовлению 125_2'
      } else if (this.selected === 'Закончились этикетки 125_2') {
        this.msg = 'Перейти к изготовлению 125_6'
      } else if (this.selected === 'Закончились этикетки 125_6') {
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
