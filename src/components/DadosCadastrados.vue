<template>
  <div class="display-container">
    <h2>Dados Cadastrados:</h2>
    <div class="data-item">
      <strong>Nome:</strong>
      <span>{{ formData.nome }}</span>
    </div>
    <div class="data-item">
      <strong>Email:</strong>
      <span>{{ formData.email }}</span>
    </div>
    <div class="data-item">
      <strong>Telefone:</strong>
      <span>{{ formData.telefone }}</span>
    </div>
    <div class="data-item">
      <strong>CPF:</strong>
      <span>{{ formData.cpf }}</span>
    </div>
    <div class="data-item">
      <strong>Endereço:</strong>
      <span>{{ formData.endereco }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DadosCadastrados',
  props: {
    formData: {
      type: Object,
      required: true,
      default: () => ({}),
    },
  },
};
</script>

<style scoped>
.display-container {
  background: linear-gradient(135deg, #ffffff, #e0e0e0);
  padding: 2rem;
  border-radius: 8px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  width: 300px;
  color: #333;
}

h2 {
  text-align: center;
  margin-bottom: 1.5rem;
  color: #333;
}

.data-item {
  margin-bottom: 1rem;
}
</style>