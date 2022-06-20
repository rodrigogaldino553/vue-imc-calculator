<template>
  <div class="imc-inputs">
    <h1>Are you health?</h1>
    <div class="fields">
      <div class="field">
        <label for="height">Height</label>
        <input name="height" type="number" v-on:input="calculate" v-model="user_height" class="height" placeholder="cm">
      </div>
      <div class="field">
        <label for="weight">Weight</label>
        <input name="weight" type="number" v-on:input="calculate" v-model="user_weight" class="weight" placeholder="kg">
      </div>
    </div>
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
        if(this.user_height !== "" && this.user_weight !== ""){
          this.user_imc = 'Your IMC is '+(this.user_weight / (Math.pow(this.user_height, 2))).toString().substring(4, 6)
        }else{
          this.user_imc = ""
        }
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

  .imc-inputs .fields{
    display: flex;
    justify-content: center;
  }

  .imc-inputs .fields .field{
    display: flex;
    flex-flow: column;
    justify-content: center;
    align-items: center;
    max-width: fit-content;
  }

  .imc-inputs .fields .field label{
    width: min-content;
    font-size: 12px;
  }

  .imc-inputs .fields .field input{
    max-width: 50px;
    max-height: 70px;
    font-size: 28px;
    padding: 15px 5px;
    border-radius: 16px;
    border:none;
    background: gainsboro;
    text-align: center;
    margin-left: 4px;
    font-weight: 600;
    color: #2c3e50;
  }

  .imc-inputs .height{
    min-width: 70px;
  }
</style>
