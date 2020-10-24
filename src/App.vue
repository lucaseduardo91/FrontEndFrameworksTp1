<template>
  <div id="app">
    <b-container>
      <div>
        <b-jumbotron header="Lista de Tarefas" lead="Status atual das tarefas que devem ser feitas">
        </b-jumbotron>
      </div>
      <b-list-group>
        <b-list-group-item :key="tarefa.id"
                            v-for="tarefa in tarefas"
                            :id="tarefa.id"
                            v-bind:class="{ concluida: tarefa.estaCompleta }">
            {{tarefa.descricao}}
        </b-list-group-item>
      </b-list-group>
    </b-container>
  </div>
</template>

<script>
import "bootstrap/dist/css/bootstrap.css";
import "bootstrap-vue/dist/bootstrap-vue.css";

export default {
  name: 'App',
  data() {
    return {
      title: "Lista de Tarefas",
      horas: new Date().getHours(),
      carrinho : [],
      tarefas : [
        { id: 1, descricao: "Lavar o Carro", estaCompleta: true },
        { id: 2, descricao: "Formatar o pc", estaCompleta: true },
        { id: 3, descricao: "Fazer o almoço", estaCompleta: false },
        { id: 4, descricao: "Fazer compras no mercado", estaCompleta: true },
        { id: 5, descricao: "Trocar a lâmpada do banheiro", estaCompleta: false },
        { id: 6, descricao: "Comprar pilhas", estaCompleta: false },
        { id: 7, descricao: "Enviar e-mail para faculdade", estaCompleta: true },
        { id: 8, descricao: "Escolher alguém em quem votar", estaCompleta: false }
      ]
    };
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
.concluida{
  background-color: aquamarine;
}
</style>
