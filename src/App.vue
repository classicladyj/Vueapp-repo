<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
  <header>
    

    <div class="wrapper">
      <p>Enter your name <input type="text" v-model="name"></p>  
      <p>Enter your state<input type="text" v-model="state"></p>  
      <h1>My name is {{name }}.I'm an indigin of {{ state }}.</h1>
    </div>

    <div class="wrapper">
      <p>Enter first number <input type="text" @change="calculate" v-model="this.number1"></p>  
      <p>Enter second number <input type="text" @change="calculate"  v-model="this.number2"></p>  
      <h1>The sum of {{number1}} and {{number2}} is {{ result }}</h1>
      
    </div>
  </header>

  <main>
    <TheWelcome />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>

<script>
export default{
data() {
  return {
      name: "",
      state: "",
    number1: 0,
    number2: 0,
    result:0
  }
},

methods : {
  calculate: function () {
  this.result = parseInt(this.number1) + parseInt(this.number2);
}
}
}
</script>
