<script setup>
import { ref } from 'vue';
import MeuComponente from './components/MeuComponente.vue';
import DadosCadastrados from './components/DadosCadastrados.vue';

// Estado reativo do formulário
const formState = ref({
  nome: '',
  email: '',
  telefone: '',
  cpf: '',
  endereco: '',
});

// Variável para controlar qual componente exibir
const showData = ref(false);

// Função para manipular o envio do formulário
const handleSubmit = (event) => {
  event.preventDefault();
  showData.value = true;
};
</script>

<template>
  <div class="centraliza">
    <main v-if="!showData">
      <h1>Cadastro de Clientes</h1>
      <form @submit="handleSubmit">
        <MeuComponente
          label="Nome:"
          placeholder="Digite seu nome"
          v-model="formState.nome"
        />
        <MeuComponente
          label="Email:"
          placeholder="Digite seu email"
          v-model="formState.email"
        />
        <MeuComponente
          label="Telefone:"
          placeholder="Digite seu telefone"
          v-model="formState.telefone"
        />
        <MeuComponente
          label="CPF:"
          placeholder="Digite seu CPF"
          v-model="formState.cpf"
        />
        <MeuComponente
          label="Endereço:"
          placeholder="Digite seu endereço"
          v-model="formState.endereco"
        />

        <button type="submit">Cadastrar</button>
      </form>
    </main>

    <DadosCadastrados v-else :formData="formState" />
  </div>
</template>

<style scoped>
.centraliza {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background: linear-gradient(135deg, #1e3c72, #2a5298);
}

main {
  background: linear-gradient(135deg, #ffffff, #e0e0e0);
  padding: 2rem;
  border-radius: 8px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  width: 300px;
}

h1 {
  text-align: center;
  margin-bottom: 1.5rem;
  color: #333;
}

form {
  display: flex;
  flex-direction: column;
}

button {
  padding: 0.75rem;
  background-color: #4caf50;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 1rem;
  margin-top: 1rem;
}

button:hover {
  background-color: #369870;
}
</style>
