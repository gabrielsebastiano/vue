import 'https://stackpath.bootstrapcdn.com/bootstrap/4.1.2/css/bootstrap.min.css'
import Vue from 'vue';


<template>
  <div id="app">
    <img src="./assets/logo.png">
     <p>{{meessage}}</p>
      <ul>
        <li v-for="produto in produtos" v-bind:key="produto">
        {{produto}}
        </li>
      </ul>
      <h2>O Total de produtos da Lista é: {{totalProdutos}}</h2>
      <input type="text"  v-model="message" placeholder="Insira aqui o produto">
    <button v-on:message="handleMessage" type="button">Enviar</button> 
  </div>
</template>

<script>
export default {
  name: "app",
  data: function() {
    return {
      meessage: "Minha Lista de Compras",
      produtos: [],
    }
  },
  computed: {
    totalProdutos() {
      return this.produtos.length;
    }
  },
  methods: {
    handleSendMessage: function () {
      this.$emit('message', { produtos: this.produtos })
    },handleMessage: function (payload) {
      this.produtos.push(payload.produtos)
    }
  }
};


</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>


