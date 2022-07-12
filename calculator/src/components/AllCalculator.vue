<template>
  <div class="w-96 border m-auto mt-16 rounded-lg" id="calculator">
    <div class="bg-purple-1 h-52 text-white m-2">
      <p class="text-right text-5xl">{{ currentValue || "0" }}</p>
    </div>

    <div id="buttons-container">
      <div class="grid grid-cols-4 text-lg gap-x-4 gap-y-4 text-slate-200 m-4">
        <button @click="clear" class="text-violet-500">AC</button>
        <button class="h-16 w-16">+/-</button>
        <button class="h-16 w-16">%</button>
        <button class="bg-zinc-400 rounded-full h-16 w-16">÷</button>
        <button @click="setValue" id="num" class="h-16 w-16">7</button>
        <button @click="setValue" id="num" class="h-16 w-16">8</button>
        <button @click="setValue" id="num" class="h-16 w-16">9</button>
        <button class="bg-zinc-400 rounded-full h-16 w-16">x</button>
        <button @click="setValue" id="num" class="h-16 w-16">4</button>
        <button @click="setValue" id="num" class="h-16 w-16">5</button>
        <button @click="setValue" id="num" class="h-16 w-16">6</button>
        <button class="bg-zinc-400 rounded-full h-16 w-16">-</button>
        <button @click="setValue" id="num" class="h-16 w-16">1</button>
        <button @click="setValue" id="num" class="h-16 w-16">2</button>
        <button @click="setValue" id="num" class="h-16 w-16">3</button>
        <button class="bg-zinc-400 rounded-full h-16 w-16">+</button>
        <button @click="setValue" id="num" class="h-16 w-16">0</button>
        <button class="h-16 w-16">.</button>
        <button class="col-start-4 bg-violet-500 rounded-full h-16 w-16">
          =
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AllCalculator",
  data() {
    return {
      currentValue: "",
      beforeNum: null,
      operator: null,
      clickedOperator: false,
    };
  },
  methods: {
    setValue(){
      this.currentValue =
    },
    clear() {
      this.valorCorrente = "";
    },
  },
};
</script>

<style scoped>
p {
  margin-top: 25%;
}

div#calculator {
  font-family: "Montserrat";
  font-weight: 400;
  background-color: #252830;
}
</style>
