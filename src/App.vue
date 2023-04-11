<script setup>
import { ref } from 'vue'

const nome = ref('')
const email = ref('')
const senha = ref('')
const confirmasenha = ref('')
const datnasci = ref('')
const endereco = ref('')
const cidade = ref('')
const estado = ref('')
const hobbies = ref('')
const linguagemprogram = ref('')
const biografia = ref('')

const enviar = ref(false)
function confirma(){
  if(senha.value != confirmasenha.value){
    alert("Senha incorreta")
  }else(
    enviar.value = !enviar.value
  )
}
</script>

<template>
  <div class="container">
    <div class="login">
      <label>Nome:</label>
      <input type="text" v-model="nome" placeholder="Nome">
      <label>Email:</label>
      <input type="email" v-model="email" placeholder="E-mail">
      <label>Senha:</label>
      <input type="password" v-model="senha" placeholder="Senha">
      <label>Confirme a senha:</label>
      <input type="password" v-model="confirmasenha" placeholder="Confirmar senha">
      <label>Data de nascimento:</label>
      <input type="date" v-model="datnasci" placeholder="Data de nascimento">
      <label>Endereço:</label>
      <input type="text" v-model="endereco" placeholder="Informe seu endereço">
      <label>Informe o estado em que vive:</label>
      <select v-model="estado">
      <option value="AC">Acre</option>
      <option value="AL">Alagoas</option>
      <option value="AP">Amapá</option>
      <option value="AM">Amazonas</option>
      <option value="BA">Bahia</option>
      <option value="CE">Ceará</option>
      <option value="DF">Distrito Federal</option>
      <option value="ES">Espírito Santo</option>
      <option value="GO">Goias</option>
      <option value="MA">Maranhão</option>
      <option value="MT">Mato Grosso</option>
      <option value="MS">Mato Grosso do Sul</option>
      <option value="MG">Minas Gerais</option>
      <option value="PA">Para</option>
      <option value="PB">Paraíba</option>
      <option value="PR">Paraná</option>
      <option value="PE">Pernambuco</option>
      <option value="PI">Piauí</option>
      <option value="RJ">Rio de Janeiro</option>
      <option value="RN">Rio Grande Norte</option>
      <option value="RS">Rio Grande do Sul</option>
      <option value="RO">Rondônia</option>
      <option value="RR">Roraima</option>
      <option value="SC">Santa Catarina</option>
      <option value="SP">São Paulo</option>
      <option value="SE">Sergipe</option>
      <option value="TO">Tocantins</option>
    </select>
    <label>Informe a cidade:</label>
  <input type="text" v-model="cidade" placeholder="Informe a cidade">
   <label>Hobbies:</label>
   <input type="text" v-model="hobbies" placeholder="Seus hobbies">
   <label>Linguagem de programação:</label>
   <input type="text" v-model="linguagemprogram" placeholder="Linguagem de programação">
   <label>Biografia:</label>
   <textarea v-model="biografia" placeholder="Biografia"></textarea>
   <button type="button" class="btn btn-primary btn block" @click="confirma" >Enviar</button>
    </div>
   
    <div class="infopessoal" v-if="enviar">
    <h3>Suas informações</h3>
    <p>Nome: {{ nome }}</p>
    <p>Email: {{ email }}</p>
    <p>Senha: {{ senha }}</p>
    <p>Confirmar senha: {{ confirmasenha }}</p>
    <p>Data de nascimento: {{ datnasci }}</p>
    <p>Endereço: {{ endereco }}</p>
    <p>Estado: {{ estado }}</p>
    <p>Cidade: {{ cidade }}</p>
    <p>Seus hobbies: {{ hobbies }}</p>
    <p>Linguagem de programação: {{ linguagemprogram }}</p>
    <p class="text-bio">Sua biografia: {{ biografia }}</p>


    </div>









  </div>
  
</template>

<style scoped>
.text-bio{
  word-wrap: break-word;
  line-break: anywhere;
}
body{
  background-color: dodgerblue;
}
.container{
  display: flex;
  justify-content: space-between;
  width: 250px;  
}
.login{
  background-color: lightblue;
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
}
.infopessoal{
  display: flex;
  background-color: lightcyan;
  align-items: center;
  flex-direction: column;
}
input{
  margin: 10px;
  margin-bottom: 10px;
  
}

</style>
