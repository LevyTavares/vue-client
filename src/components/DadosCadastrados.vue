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
  name: "DadosCadastrados",
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
  background: linear-gradient(135deg, #23272f 60%, #282828 100%);
  padding: 2rem;
  border-radius: 16px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.25);
  width: 340px;
  color: #eee;
}

h2 {
  text-align: center;
  margin-bottom: 1.5rem;
  color: #28a745;
  font-weight: 500;
  letter-spacing: 1px;
}

.data-item {
  margin-bottom: 1rem;
  display: flex;
  gap: 0.5rem;
  align-items: center;
  background: #222;
  padding: 0.5rem 1rem;
  border-radius: 8px;
}

strong {
  color: #28a745;
  min-width: 90px;
}

span {
  color: #fff;
  font-weight: 400;
}
</style>
