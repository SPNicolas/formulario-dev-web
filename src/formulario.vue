<script setup>
  import { ref } from 'vue';
  const senha = ref('');
  const nome = ref('');
  const idade = ref('');
  const aceitaTermos = ref(false);
</script>

<template>
  <div class="formulario">
    <div class="pessoal">
      <input type="text" v-model="nome" placeholder="Digite seu nome" />
      <label for=""></label>
    </div>


  </div>
  
</template>


<style scoped>
    .formulario {
      display: flex;
      justify-content: center;
      align-items: center;
      border: 1px solid white;
    }
    .formulario .pessoal {
      display: flex;
      justify-content: center;
      align-items: center;
    }

</style>
