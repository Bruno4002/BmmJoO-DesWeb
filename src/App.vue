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
      <input type="text" v-model="nome" placeholder="Nome">
      <hr>
      <input type="email" v-model="email" placeholder="E-mail">
      <hr>
      <input type="password" v-model="senha" placeholder="Senha">
      <hr>
      <input type="password" v-model="confirmasenha" placeholder="Confirmar senha">
      <hr>
      <input type="date" v-model="datnasci" placeholder="Data de nascimento">
      <hr>
      <input type="text" v-model="endereco" placeholder="Informe seu endereço">
      <hr>
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

      
    </div>
    <button @click="confirma">Enviar</button>
    <div class="infopessoal" v-if="enviar">
    <h3>Suas informações</h3>
    <p>Nome: {{ nome }}</p>
    <p>Email: {{ email }}</p>
    <p>Senha: {{ senha }}</p>
    <p>Confirmar senha: {{ confirmasenha }}</p>
    <p>Data de nascimento: {{ datnasci }}</p>
    <p>Endereço: {{ endereco }}</p>
    <p>Estado: {{ estado }}</p>


    </div>









  </div>
  
</template>

<style scoped>
</style>
