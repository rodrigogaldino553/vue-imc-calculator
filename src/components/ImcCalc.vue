<template>
  <div class="imc-inputs">
    <h1>Are you health?</h1>
    <input type="number" v-model="user_height" class="height" placeholder="cm">
    <input type="number" v-on:input="calculate" v-model="user_weight" class="weight" placeholder="kg">
    <!-- button v-on:click="calculate">See IMC</button-->
    <h2>{{user_imc}}</h2>
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
  .imc-inputs{
    border-radius: 4px;
    box-shadow: 2px 2px 5px gray;
    max-width: 300px;
    padding: 20px;
    margin: auto;
  }

  .imc-inputs input{
    max-width: 50px;
    max-height: 70px;
    font-size: 28px;
    padding: 15px 5px;
    border-radius: 16px;
    border:none;
    background: gainsboro;
    text-align: center;
    margin-left: 4px;
  }

  .imc-inputs .height{
    max-width: 70px;
  }
</style>
