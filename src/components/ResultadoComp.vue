<script setup>

defineProps(['dadosPerfil'])

</script>
<template>

<div v-if="mostrarResultado" class="resultado">
  <div class="row">
  <h2>Dados do cadastro</h2>
  <p>Nome: {{ dadosPerfil.nome }}</p>
  <p>Email: {{ dadosPerfil.email }}</p>
  <p>Senha: {{ dadosPerfil.senha }}</p>
  <p>confirmar senha: {{ dadosPerfil.confirmarSenha }}</p>
  <p>Data de nascimento: {{ dadosPerfil.data }}</p>
  <p>Seu endereco: {{ dadosPerfil.endereco }}</p>
  <p>Sua cidade: {{ dadosPerfil.cidade }}</p>
  <p>Seu estado: {{ dadosPerfil.estadoSelecionado }}</p>
  <p>Hobbies: {{ dadosPerfil.hobbies }}</p>
  <p>Linguagens: {{ dadosPerfil.linguagens }}</p>
  <p>Biografia: {{ dadosPerfil.biografia }}</p>
  </div> 
</div>

</template>
<style scoped>

</style>