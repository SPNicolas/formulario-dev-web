<script setup>

  import { ref, reactive } from 'vue';

  const dados = ref({
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
    
    <form @submit.prevent="$emit('enviar', {...dados})">

        <h2>Formulário para cadastro do produto</h2>

        <div class="row">
          <label for="">Nome:</label>
          <input type="text" v-model="dados.nome" size="20" maxlength="20" minlength="3" required/>
        </div>

        <div class="row">
          <label for="">Digite seu email:</label>
          <input type="email" v-model="dados.email" required/>
        </div>

        <div class="row">
          <label for="">Senha:</label>
          <input type="password" v-model="dados.senha" required/>
        </div>

        <div class="row">
          <label for="">Confirme sua senha:</label>
          <input type="password" v-model="dados.confirmarSenha" required/>
        </div>
        
        <div class="row">
          <label for="">Data de nascimento</label>
          <input type="date" v-model="dados.data">
        </div>

        <div class="row">
          <label for="">Seu endereço:</label>
          <input type="text" v-model="dados.endereco"/>
        </div>
        
        <div class="row">
          <label for="">Sua cidade:</label>
          <input type="text" v-model="dados.cidade" />
        </div>

        <div class="estado">
          <label for="">Estado:</label>
          <select name="" id="" v-model="dados.estadoSelecionado">
          <option v-for="(estado, index) in estados" :key="index" :value="estado">{{ estado }}</option>
          </select>
        </div>

        <div class="row">
          <label for="">Hobbies:</label>
          <input type="radio" value="Brincar" v-model="dados.hobbies"/> Brincar
          <input type="radio" value="Ler" v-model="dados.hobbies"/> Ler
          <input type="radio" value="Treinar" v-model="dados.hobbies"/> Treinar
          <input type="radio" value="Jogar videogame" v-model="dados.hobbies"/> Jogar videogame
          <input type="radio" value="Escutar músicas" v-model="dados.hobbies"/> Escutar músicas
          <input type="radio" value="Jogar futebol" v-model="dados.hobbies"/> Jogar futebol
        </div>

        <div class="row">
          <label for="">Linguagens:</label>
          <input type="radio" value="Python" v-model="dados.linguagens"/> Python
          <input type="radio" value="JavaScript" v-model="dados.linguagens"/> JavaScript
          <input type="radio" value="PHP" v-model="dados.linguagens"/> PHP
          <input type="radio" value="CSS" v-model="dados.linguagens"/> CSS
        </div>

        <div class="biografia">
          <label for="">Biografia:</label>
          <textarea name="" id="" cols="30" rows="10" v-model="dados.biografia" ></textarea>
        </div>

        <input id="botao" type="submit" value="Enviar">

    </form>

  </div>


</template>
<style scoped>

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
.biografia {
    width: 400px;
    display: flex;
    justify-content: space-between;
}

form{
  background-color: #3d3d3d;
  border-radius: 20px;
  height: 100%;
  margin-left: 30px;
  margin-right: 30px;
  margin-bottom: 20px;
  margin-top: 30px;
  text-align: left;
}

.row {
  padding: 30px;
  display: flex;
  justify-content: space-between;
  width: 500px;
}

#botao {
  margin-top: 20px;
  margin-bottom: 20px;
}
</style>