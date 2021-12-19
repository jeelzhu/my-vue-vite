<script setup lang="ts">
import { ref } from 'vue'

defineProps<{ msg: string }>()

const amount = ref(10000)
const rate = ref(0.1)
const year = ref(10)
const result = ref(0)

const calculate = () => {
  let  totalAmount:number = parseFloat(amount.value);
  console.log(totalAmount)
  for ( let i=1;i < parseInt(year.value); i++) {
    totalAmount += totalAmount*parseFloat(rate.value) ;
    console.log(totalAmount)

  }
  result.value = totalAmount.toFixed(2)
}

calculate();
</script>

<template>
  <h1>{{ msg }}</h1>
  <ul>
    <label>Initial amount:</label>
    <input id="amount" v-model="amount" @change="calculate"/> <br/>
    <label>Interest rate</label> <input id="rate" v-model="rate" @change="calculate" /> <br/>
    <label>Year</label> <input id="year" v-model="year"  @change="calculate"/> <br/>
    <label>{{result}}</label><br/>
  </ul>
</template>

<style scoped>
a {
  color: #42b983;
}

label {
  margin: 0 0.5em;
  font-weight: bold;
}

code {
  background-color: #eee;
  padding: 2px 4px;
  border-radius: 4px;
  color: #304455;
}
</style>
