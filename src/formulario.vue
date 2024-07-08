<!-- eslint-disable vue/multi-word-component-names -->

<script setup>
 import { ref, reactive } from 'vue';
 const titulo = ref('Formulário de Cadastro');
const cadastro = reactive({
  nome: '',
  email: '',
  senha: '',
  confirmarSenha: '',
  medida: '',
  categorias: [],
});
const categorias = [
  {
    id: 1,
    nome: 'Eletrônicos',
  },
  {
    id: 2,
    nome: 'Vestuário',
  },
  {
    id: 3,
    nome: 'Brinquedos',
  },
  {
    id: 4,
    nome: 'Móveis',
  },
  {
    id: 5,
    nome: 'Alimentos',
  },
  {
    id: 6,
    nome: 'Bebidas',
  },
  {
    id: 7,
    nome: 'Informática',
  },
  {
    id: 8,
    nome: 'Papelaria',
  },
];
const mostrarResultado = ref(false);


function buscarNome(id) {
  return categorias.find((categoria) => categoria.id === id).nome;
}
</script>

<template>

  <h1>{{ titulo }}</h1>
  <div class="container">
    
  <div class="formulario">
    <h2>Formulário para cadastro do produto</h2>
    <div class="row">
      <label for="">Nome:</label>
      <input type="text" v-model="cadastro.nome" size="20" maxlength="20" minlength="3"/>
    </div>
    <div class="row">
      <label for="">Digite seu email:</label>
      <input type="email" step="0.01" v-model="cadastro.email" />
    </div>
    <div class="row">
      <label for="">Senha:</label>
      <input type="password" v-model="cadastro.senha" />
    </div>
    <div class="row">
      <label for="">Confirme sua senha:</label>
      <input type="password" v-model="cadastro.confirmarSenha" />
    </div>

    <fieldset>
      <legend>Unidade de medida</legend>
      <div class="items-radiobox">
        <input type="radio" value="unidade" v-model="cadastro.medida" /> Unidades
        <input type="radio" value="peso" v-model="cadastro.medida" /> Peso
      </div>
    </fieldset>
    <fieldset>
      <legend>Categorias</legend>
      <div class="items-checkbox">
        <template v-for="categoria in categorias" :key="categoria.id">
          <input
            type="checkbox"
            :value="categoria.id"
            v-model="cadastro.categorias"
          />
           {{ categoria.nome }} 
        </template>
      </div>
    </fieldset>
    <button @click="mostrarResultado = !mostrarResultado">Mostrar</button>
  </div>
</div>
<div v-if="mostrarResultado" class="resultado">
  <h2>Dados do cadastro</h2>
  <p>Nome: {{ cadastro.nome }}</p>
  <p>Email: {{ cadastro.email }}</p>
  <p>Senha: {{ cadastro.senha }}</p>
  <p>Medida: {{ cadastro.medida }}</p>
  <p>Categorias: {{ cadastro.categorias }}</p>
  <h4>Categorias selecionadas:</h4>
  <p v-for="categoria_id in cadastro.categorias" :key="categoria_id">
    - {{ buscarNome(categoria_id) }}
  </p>
</div>

  
</template>
<div class="container">

  </div>




<style scoped>
.altera-titulo {
  background-color: #98e0aa;
  margin: 1rem 2rem;
  border-radius: 20px;
  padding: .75rem;
  display: flex;
  gap: 1rem
}

.container {
  display: flex;
  justify-content: flex-start;
  gap: 2rem;
  margin-top: 1rem;
  padding: 0 2rem;
}

.formulario,
.resultado {
  width: 45vw;
  min-height: 70vh;
  border-radius: 20px;
  padding: 20px;
}

.formulario {
  background-color: #d29696;
}

.formulario .row {
  width: 80%;
  margin: 1.3rem 0;
  display: flex;
  justify-content: space-between;
}

.items-checkbox,
.items-radiobox {
  display: grid;
  grid-template-columns: auto 1fr;
  align-items: center;
}

.resultado {
  background-color: #98e0aa;
}

button {
  padding: 0.5rem 1rem;
  border: none;
  background-color: #f1f1f1;
  border-radius: 10px;
  cursor: pointer;
}

button:hover {
  background-color: #e1e1e1;
}
input {
  width: 400px;
  padding: 10px;
  font-size: 24px;
  border-radius: 10px;
  border: 1px solid transparent;
}

input[type='checkbox'],
input[type='radio'] {
  width: 20px;
  height: 20px;
  margin: 0 10px;
}

input:hover {
  border: 1px solid black;
}
</style>