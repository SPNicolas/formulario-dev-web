<script setup>
 import { ref, reactive } from 'vue';
    const cadastro = reactive({
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
});

const estados = reactive([
"AC", "AL", "AP", "AM", "BA", "CE", "DF", "ES", "GO", "MA", "MT", "MS", "MG", "PA", "PB", "PR", "PE", "PI", "RJ", "RN", "RS", "RO", "RR", "SC", "SP", "SE", "TO"
])


</script>
<template>
    <div class="container">
    
    <div class="formulario">
      <h2>Formulário para cadastro do produto</h2>
      <div class="row">
        <label for="">Nome:</label>
        <input type="text" v-model="cadastro.nome" size="20" maxlength="20" minlength="3"/>
      </div>
      <div class="row">
        <label for="">Digite seu email:</label>
        <input type="email" v-model="cadastro.email" required/>
      </div>
      <div class="row">
        <label for="">Senha:</label>
        <input type="password" v-model="cadastro.senha" required/>
      </div>
      <div class="row">
        <label for="">Confirme sua senha:</label>
        <input type="password" v-model="cadastro.confirmarSenha" required/>
      </div>
      <div class="row">
        <label for="">Data de nascimento</label>
        <input type="date" v-model="cadastro.data">
      </div>
      <div class="row">
        <label for="">Seu endereço:</label>
        <input type="text" v-model="cadastro.endereco" required/>
      </div>
      <div class="row">
        <label for="">Sua cidade:</label>
        <input type="text" v-model="cadastro.cidade" />
      </div>
      <div class="estado">
        <label for="">Estado:</label>
        <select name="" id="" v-model="cadastro.estadoSelecionado">
          <option v-for="(estado, index) in estados" :key="index" value="">{{ estado }}</option>
        </select>
      </div>
      <div class="row">
        <label for="">Hobbies:</label>
        <input type="radio" value="Brincar" v-model="cadastro.hobbies"/> Brincar
        <input type="radio" value="Ler" v-model="cadastro.hobbies"/> Ler
        <input type="radio" value="Treinar" v-model="cadastro.hobbies"/> Treinar
        <input type="radio" value="Jogar videogame" v-model="cadastro.hobbies"/> Jogar videogame
        <input type="radio" value="Escutar músicas" v-model="cadastro.hobbies"/> Escutar músicas
        <input type="radio" value="Jogar futebol" v-model="cadastro.hobbies"/> Jogar futebol
      </div>
      <div class="row">
        <label for="">Linguagens:</label>
        <input type="radio" value="Python" v-model="cadastro.linguagens"/> Python
        <input type="radio" value="JavaScript" v-model="cadastro.linguagens"/> JavaScript
        <input type="radio" value="PHP" v-model="cadastro.linguagens"/> PHP
        <input type="radio" value="CSS" v-model="cadastro.linguagens"/> CSS
      </div>
      <div class="biografia">
        <label for="">Biografia:</label>
        <textarea name="" id="" cols="30" rows="10" v-model="cadastro.biografia" ></textarea>
      </div>


    <button @click="mostrarResultado = !mostrarResultado">Mostrar</button>

    
  </div>
</div>
<div v-if="mostrarResultado" class="resultado">
  <div class="row">
  <h2>Dados do cadastro</h2>
  <p>Nome: {{ cadastro.nome }}</p>
  <p>Email: {{ cadastro.email }}</p>
  <p>Senha: {{ cadastro.senha }}</p>
  <p>confirmar senha: {{ cadastro.confirmarSenha }}</p>
  <p>Data de nascimento: {{ cadastro.data }}</p>
  <p>Seu endereco: {{ cadastro.endereco }}</p>
  <p>Sua cidade: {{ cadastro.cidade }}</p>
  <p>Seu estado: {{ cadastro.estadoSelecionado }}</p>
  <p>Hobbies: {{ cadastro.hobbies }}</p>
  <p>Linguagens: {{ cadastro.linguagens }}</p>
  <p>Biografia: {{ cadastro.biografia }}</p>
  </div> 
</div>

</template>
<style scoped>
    .container {
  display: flex;
  justify-content: flex-start;
  gap: 2rem;
  margin-top: 1rem;
  padding: 0 2rem;
}

.formulario {
  width: 100%;
  min-height: 600px;
  border-radius: 20px;
  padding: 20px;
}
.formulario {
  background-color: #92a6ff;
}

.formulario .row {
  width: 80%;  line-height: 40px;
  margin: 1.3rem 0;
  display: flex;
  justify-content: space-between;
}

.formulario .estado {
  display: flex;
  justify-content: space-between;
  width: 200px;
}

.items-checkbox,
.items-radiobox {
  display: grid;
  grid-template-columns: auto 1fr;
  align-items: center;
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
.resultado {
  background-color: #98e0aa;
  border-radius: 20px;
  height: 500px;
  margin-left: 30px;
  margin-right: 30px;
  margin-bottom: 20px;
  margin-top: 30px;
  text-align: left;

}
.biografia {
    width: 400px;
    display: flex;
    justify-content: space-between;
}

.resultado .row {
    padding: 30px;
}

</style>