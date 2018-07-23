import 'https://stackpath.bootstrapcdn.com/bootstrap/4.1.2/css/bootstrap.min.css'


<template>
  <div id="app">
    <img src="./assets/logo.png">
     <p>{{meessage}}</p>
      <ul>
        <li v-for="produto in produtos" v-bind:key="produtos">
        {{produto}}
        </li>
      </ul>
      <h2>O Total de produtos da Lista é: {{totalProdutos}}</h2>
      <input type="text" v-model="meessage">
    <button class="btn btn-primary" @click="apagar" type="button">Limpar</button> 
  
  </div>
</template>

<script>
export default {
  name: "app",
  data: function() {
    return {
      meessage: "TABELA DA PUTARIA",
      produtos: ["gabriel", "junior", "junior", "felipe"]
    };
  },
  computed: {
    totalProdutos() {
      return this.produtos.length
    }
  },
  methods: {
    apagar: function() {
      this.meessage = "";
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


