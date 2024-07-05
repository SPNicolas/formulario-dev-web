<script setup>
  import { ref } from 'vue';
  const nome = ref('');
  const sexo = ref('')
</script>

<template>
  <input type="text" v-model="nome"  placeholder="Digite seu nome" style="width: 200px"/>
  <label for="text">O texto o nome colocado é: {{ nome }}</label>
  <label for="sexo">Sexo</label>
  <input type="radio" v-model="sexo" value="masculino" /> Masculino
  <input type="radio" v-model="sexo" value="feminino" /> Feminino
  <label>Sexo: {{ sexo }}</label>
  <input type="password" v-model="senha" required />
  <label for="text">Confirme a senha</label>
  <input type="password" v-model="senha" required/>

</template>


<style scoped>

</style>
