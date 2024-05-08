<template>
  <div id="app">
    <h1>Rock Paper Scissors Game</h1>
    <p>Please pick your option to start game</p>
    <img id="rock" v-on:click="selectOption('rock')" src="https://nationaltoday.com/wp-content/uploads/2021/08/National-Pet-Rock-Day-1200x834.jpg" height="100">
    <img id="paper" v-on:click="selectOption('paper')" src="https://www.paperpapers.com/media/catalog/product/cache/040ab45878687996a103a8acd78a7429/p/l/plike-white-811.jpg" height="100">
    <img id="scissors" v-on:click="selectOption('scissors')" src="https://m.media-amazon.com/images/I/61M-ByG5XoL.__AC_SX300_SY300_QL70_FMwebp_.jpg" height="100">
    <h2>User's choice:</h2>
    <p>{{ userChoice }}</p>
    <h2>Computer's choice:</h2>
    <p>{{ cpuChoice }}</p>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'App',
  data() {
    return{
    userChoice: "",
    cpuChoice: ""
  }
},
methods:{
  async selectOption(option){
    this.userChoice = option;

    const response = await axios.post("https://3f7a-201-174-123-50.ngrok-free.app/jugar", {
      opcionJugador1: this.userChoice
    });
  }
}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
