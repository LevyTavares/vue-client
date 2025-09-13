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
  <header class="header">
    <h2 class="titulo">Formulário de Cadastro</h2>
    <p class="subtitulo">Preencha os campos abaixo:</p>
  </header>
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
  <footer class="footer">
    <p>&copy; 2024 Seu Nome. Todos os direitos reservados.</p>
    <p>Meu GitHub: <a href="https://github.com/LevyTavares" target="_blank">fnuf</a></p>
  </footer>
</template>

<style scoped>
.header {
  text-align: center;
  background-color: #1e2a38;
  color: white;
  padding: 1.5rem 0;
  border-bottom: 1px solid var(--color-border);
}

.centraliza {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  padding: 2rem;
  background: linear-gradient(135deg, #121212, #1e1e1e);
}

main {
  background: #282828;
  padding: 2.5rem;
  border-radius: 16px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.25);
  width: 100%;
  max-width: 400px;
}

h1 {
  text-align: center;
  margin-bottom: 2rem;
  color: var(--color-heading);
}

form {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

button {
  padding: 0.85rem;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  font-size: 1rem;
  margin-top: 1.5rem;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #0056b3;
}

.footer {
  text-align: center;
  background-color: #1e2a38;
  color: var(--color-text);
  padding: 1.5rem 0;
  width: 100%;
  border-top: 1px solid var(--color-border);
}

.footer a {
  color: #007bff;
}
</style>
