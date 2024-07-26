
<script setup>

  import { ref } from 'vue'

  import FormsComp from './components/FormsComp.vue'
  import ResultadoComp from './components/ResultadoComp.vue'

  const cadastro = ref(
    {
    nome: '',
    email: '',
    senha: '',
    confirmarSenha: '',
    data: '',
    endereco: '',
    cidade: '',
    hobbies: '',
    linguagens: '',
    estadoSelecionado: '',
    biografia: '',
    }
  );

  const botao = ref(false)

  function enviar(dados) {
    cadastro.value = dados
    botao.value = true
  }
  
  function voltar(){
    botao.value = false
  }

</script>

<template>

  <FormsComp v-if="!botao" @enviar = "enviar"></FormsComp>
  <ResultadoComp v-if="botao" :dados-perfil="cadastro" @voltar="voltar()"></ResultadoComp>

</template>

<style scoped>

</style>