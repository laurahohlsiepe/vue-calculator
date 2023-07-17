<template>
  <header class="text-green-700 text-3xl text-center mb-16 mt-2">
    Vue.js Calculator
  </header>
  <body>
   <div class="border-2 border-green-400 grid grid-rows-4 grid-cols-4 sm:mx-52 bg-green-200">
    <div class="col-start-1 col-end-5 text-center mt-3 font-bold text-lg py-4">{{ value || '0' }}</div>

    <div v-for="n in calculatorElements" :key="n" class="rounded hover:bg-green-600 py-4 m-1"
    :class="{'bg-green-300': ['C', '*', '/', '-', '%', '+', '='].includes(n)}"
    @click="action(n)">
      <div class="font-bold text-lg text-center">
       {{ n }}       
      </div>

    </div>
   </div> 
  </body>
</template>

<script>
export default {
  name: 'calculator',
  data() {
    return {
         value: '',
         calculatorElements: ['C', '*', '/', '-', 7, 8, 9, '%', 4, 5, 6, '+', 3, 2, 1, '=', 0, '.'],
         operator: null,
         previousValue: ''
    }
  },
  methods: {
    action(n) {
      if(!isNaN(n) || n === '.') {
        this.value += n + '';
      }

      if(n === 'C') {
        this.value = '';
      }

      if(n === '%') {
        this.value = this.value / 100 + '';
      }

      if(['*', '/', '-', '+'].includes(n)) {
        this.operator = n;
        this.previousValue = this.value;
        this.value = '';
      }

      if(n === '=') {
        this.value = eval(
          this.previousValue+ this.operator + this.value
        );

        this.previousValue = '';
        this.operator = null;
      }
    },
  }
} 
</script>
