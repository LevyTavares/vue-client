<template>
  <div class="form-field">
    <label>{{ label }}</label>
    <input
      :placeholder="placeholder"
      type="text"
      :value="modelValue"
      @input="$emit('update:modelValue', $event.target.value)"
    />
  </div>
</template>

<script>
export default {
  name: "MeuComponente",
  props: {
    label: {
      type: String,
      required: true,
    },
    placeholder: {
      type: String,
      required: true,
    },
    modelValue: {
      type: String,
      default: "",
    },
  },
  emits: ["update:modelValue"],
};
</script>

<style scoped>
.form-field {
  margin-bottom: 1rem;
  display: flex;
  flex-direction: column;
}

label {
  margin-bottom: 0.5rem;
  font-weight: 600;
  color: #28a745;
  letter-spacing: 0.5px;
  font-size: 1rem;
}

input {
  width: 100%;
  padding: 0.7rem;
  border: 1px solid #444;
  border-radius: 8px;
  background: #222;
  color: #eee;
  font-size: 1rem;
  transition: border-color 0.2s, box-shadow 0.2s;
  box-sizing: border-box;
}

input:focus {
  border-color: #28a745;
  box-shadow: 0 0 0 2px #28a74544;
  outline: none;
}
</style>
