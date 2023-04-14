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
const linguagemprogram = ref([])
const biografia = ref('')

const enviar = ref(false)
function confirma(){
  if(senha.value != confirmasenha.value){
    alert("Senha e confirmação não conferem")
    return false
  }else{
     return true
}
}
</script>

<template>
  <div class="container">
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
    <p>Linguagem de programação: {{ linguagemprogram.join(", ") }}</p>
    <p class="text-bio">Sua biografia: {{ biografia }}</p>
    </div>


  

    <div v-else>
      <form @submit.prevent="enviar= confirma()">
    <div class="login">
      <h2>Faça o login</h2>
      <label>Nome:</label>
      <input type="text" minlength="3" required v-model="nome" placeholder="Nome">
      <label>Email:</label>
      <input type="email" minlength="5" required v-model="email" placeholder="E-mail">
      <label>Senha:</label>
      <input type="password" minlength="6" required v-model="senha" placeholder="Senha">
      <label>Confirme a senha:</label>
      <input type="password" minlength="6" required v-model="confirmasenha" placeholder="Confirmar senha">
      <label>Data de nascimento:</label>
      <input type="date" v-model="datnasci" placeholder="Data de nascimento">
      <label>Endereço:</label>
      <input type="text" minlength="6" required v-model="endereco" placeholder="Informe seu endereço">
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
  <input type="text" minlength="3" required v-model="cidade" placeholder="Informe a cidade">
   <label>Hobbies:</label>
   <input type="text" minlength="3" required v-model="hobbies" placeholder="Seus hobbies">
   
   <label for="linguagemprogram">Linguagem de programação:</label>
   <p>
   Java<input type="checkbox" v-model="linguagemprogram" value="Java"/>
   Python<input type="checkbox" v-model="linguagemprogram" value="Python"/>
   JavaScript<input type="checkbox" v-model="linguagemprogram" value="JavaScript"/>
  </p>
   <label>Biografia:</label>
   <textarea v-model="biografia" minlength="10" maxlength="250" placeholder="Biografia"></textarea>
   <button type="submit" class="btn btn-dark ">Enviar</button>
    </div>
  </form>
</div>
    



</div>


</template>

<style scoped>
.text-bio{
  word-wrap: break-word;
  line-break: anywhere;
}
.container{
  display: flex;
  justify-content: space-around;
  width: 100%;  
}
.login{
margin-top: 15px;
  display: flex;
  flex-direction: column;
  background-color: white;
  border-radius: 15px;
  align-items: center;
  padding: 20px;
  width: 500px;
  color: rgb(0, 0, 0);
  margin-bottom: 20px;

}
.infopessoal{
  margin-top: 15px;
  display: grid;
  grid-template-columns: 1fr;
  background-color: white;
  border-radius: 15px;
  width: 500px;
  padding: 50px;
  color: rgb(0, 0, 0);
  margin-bottom: 20px;

}
input{
  margin: 10px;
  margin-bottom: 10px;
  border: 5px solid black;
  border-radius: 10px;
  
}
button{
  margin-top: 10px;
  width: 100%;
  font-size: large;
}
</style>
