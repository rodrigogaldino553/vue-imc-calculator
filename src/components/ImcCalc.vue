<template>
  <div class="imc-inputs">
    <input type="number" v-model="user_height" class="height" placeholder="Height (cm)">
    <input type="number" v-on:input="calculate" v-model="user_weight" class="weight" placeholder="Weight (kg)">
    <button v-on:click="calculate">See IMC</button>
    <h2>Your BMI is {{user_imc}}</h2>
  </div>
</template>

<script>
  export default {
    name: 'ImcCalc',
    proprs: [],
    data(){
      return {
        user_height: "",
        user_weight: "",
        user_imc: ""
      }
    }, 
    methods: {
      calculate(){
        this.user_imc = 'Your IMC is '+(this.user_weight / (Math.pow(this.user_height, 2))).toString().substring(4, 6)
      },

      category(){
        // func
      }
    }
  }
</script>

<style scoped>
</style>
