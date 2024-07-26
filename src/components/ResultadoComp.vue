<script setup>

const props = defineProps({
  dadosPerfil: {
    type: Object,
    required: true
  }
});
</script>
<template>

<div class="resultado">
  <div class="row">
  <h2>Dados do cadastro</h2>
  <p>Nome: {{ props.dadosPerfil.nome }}</p>
  <p>Email: {{ props.dadosPerfil.email }}</p>
  <p>Senha: {{ props.dadosPerfil.senha }}</p>
  <p>confirmar senha: {{ props.dadosPerfil.confirmarSenha }}</p>
  <p>Data de nascimento: {{ props.dadosPerfil.data }}</p>
  <p>Seu endereco: {{ props.dadosPerfil.endereco }}</p>
  <p>Sua cidade: {{ props.dadosPerfil.cidade }}</p>
  <p>Seu estado: {{ props.dadosPerfil.estadoSelecionado }}</p>
  <p>Hobbies: {{ props.dadosPerfil.hobbies }}</p>
  <p>Linguagens: {{ props.dadosPerfil.linguagens }}</p>
  <p>Biografia: {{ props.dadosPerfil.biografia }}</p>
  </div> 
  <div>
    <input @click="$emit('voltar')" type="button" value="Voltar">
  </div>
</div>

</template>
<style scoped>

</style>