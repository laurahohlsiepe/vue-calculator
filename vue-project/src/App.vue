<template>
  <header class="text-green-700 text-3xl text-center mb-16 mt-2">
    Vue.js Calculator
  </header>
  <body>
   <div class="border-2 border-green-400 grid grid-rows-5 grid-cols-4 h-80 sm:mx-52 bg-green-200">
    <div class="col-start-1 col-end-5 text-center mt-3 font-bold text-lg">{{ value || '0' }}</div>

      <input type="button" class="hover:bg-green-600 font-bold text-lg" value="7" @click="display('7')">
      <input type="button" class="hover:bg-green-600 font-bold text-lg" @click="display(8)" value="8">
      <input type="button" class="hover:bg-green-600 font-bold text-lg" @click="display(9)" value="9">
      <input type="button" class="hover:bg-green-600 font-bold text-lg" value="x">
      <input type="button" class="hover:bg-green-600 font-bold text-lg" @click="display(4)" value="4">
      <input type="button" class="hover:bg-green-600 font-bold text-lg" @click="display(5)" value="5">
      <input type="button" class="hover:bg-green-600 font-bold text-lg" @click="display(6)" value="6">
      <input type="button" class="hover:bg-green-600 font-bold text-lg" value="÷">
      <input type="button" class="hover:bg-green-600 font-bold text-lg" @click="display(1)" value="1">
      <input type="button" class="hover:bg-green-600 font-bold text-lg" @click="display(2)" value="2">
      <input type="button" class="hover:bg-green-600 font-bold text-lg" @click="display(3)" value="3">
      <input type="button" class="hover:bg-green-600 font-bold text-lg" @click="plus" value="+">
      <input type="button" class="hover:bg-green-600 font-bold text-lg" value="C" @click="clear()">
      <input type="button" class="hover:bg-green-600 font-bold text-lg" @click="display(0)" value="0">
      <input type="button" class="hover:bg-green-600 font-bold text-lg" value="=">
      <input type="button" class="hover:bg-green-600 font-bold text-lg" value="-">
   </div> 
  </body>
</template>

<script>
export default {
  name: 'calculator',
  data() {
    return {
         value: '',
    }
  },
  methods: {
    display(value) {
      return this.value = value;
    },
    clear() {
      return this.value = '';
    }
  }
} 
</script>
