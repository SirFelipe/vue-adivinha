<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    Adivinhe um número de 0 a 100:
    <Entrada v-on:mudou="atualizaNumero"/>
    <br>
    <Button texto="Checar número" classe="btn btn-outline-primary" alerta="Este é um alerta" fundo="" v-on:clicou="this.checarNumero"/>
    <br>
    <Button texto="Reiniciar" classe="btn btn-outline-danger" fundo="" v-on:clicou="this.reiniciar"/>
    <br>
    <Saida :sorteado="numero" :adivinhado="valor" style="color: green"/>
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import Entrada from './components/Entrada.vue'
import Button from './components/Button.vue'
import Saida from './components/Saida.vue'

export default {
  name: 'app',
  components: {
    Entrada,
    Button,
    Saida
  },
  data(){
    return { valor: "", numero: Math.floor(Math.random() * 101)}
  },
  methods: {
    //Recebendo o valor de outro componente
    atualizaNumero(txtNum){
      this.valor = txtNum;
    },
    checarNumero(){
      if(this.valor == this.numero){
        //alert("Acertou mizeravi!");
      }else if(this.valor < this.numero){
        //alert("Tente um número maior.");
      }else if(this.valor > this.numero){
        //alert("Tente um número menor");
      }else{
        //alert("Entrada inválida");
      }
    },
    reiniciar(){
      this.numero = Math.floor(Math.random() * 101);
      this.$refs.entrada.limpa();
    }
  }
}
</script>

<style lang="scss">
      @import '../node_modules/bootstrap/scss/bootstrap.scss';

      #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
      }
</style>
