<template>
  <form @submit.prevent="submitForm" class="form">
    <h2>Registro</h2>

    <div class="input-group">
      <label for="nombre">Nombre:</label>
      <input id="nombre" v-model="formData.nombre" type="text" required />
    </div>

    <div class="input-group">
      <label for="email">Correo Electrónico:</label>
      <input id="email" v-model="formData.email" type="email" required :class="{ 'input-error': !emailValido }" />
      <p v-if="!emailValido && formData.email" class="error">Ingrese un email válido</p>
    </div>

    <div class="input-group">
      <label for="password">Contraseña:</label>
      <input 
        id="password" 
        v-model="formData.password" 
        type="password" 
        required 
        minlength="6"
        :class="{ 'input-error': formData.password.length > 0 && formData.password.length < 6 }" 
      />
      <p v-if="formData.password.length > 0 && formData.password.length < 6" class="error">
        La contraseña debe tener al menos 6 caracteres
      </p>
    </div>

    <button type="submit" :disabled="!formularioValido">Enviar</button>

    <p v-if="mensaje" class="success">{{ mensaje }}</p>
  </form>
</template>

<script>
export default {
  data() {
    return {
      formData: {
        nombre: '',
        email: '',
        password: ''
      },
      mensaje: ''
    };
  },
  computed: {
    emailValido() {
      return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(this.formData.email);
    },
    formularioValido() {
      return this.formData.nombre.trim() && this.emailValido && this.formData.password.length >= 6;
    }
  },
  methods: {
    submitForm() {
      this.mensaje = "¡Formulario enviado con éxito!";
      setTimeout(() => {
        this.mensaje = "";
      }, 3000);
    }
  }
};
</script>

<style scoped>
.form {
  display: flex;
  flex-direction: column;
  gap: 15px;
  max-width: 400px;
  margin: 20px auto;
  padding: 25px;
  border-radius: 10px;
  background: linear-gradient(135deg, #6a11cb, #2575fc);
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
  color: white;
}

h2 {
  text-align: center;
  margin-bottom: 15px;
  font-size: 1.5rem;
}

.input-group {
  display: flex;
  flex-direction: column;
  gap: 5px;
}

label {
  font-weight: bold;
  font-size: 14px;
}

input {
  padding: 10px;
  border-radius: 5px;
  border: 2px solid transparent;
  font-size: 14px;
  transition: 0.3s;
}

input:focus {
  border-color: #42b983;
  outline: none;
  box-shadow: 0 0 5px rgba(66, 185, 131, 0.6);
}

.input-error {
  border-color: red !important;
  background-color: rgba(255, 0, 0, 0.1);
}

button {
  padding: 12px;
  background-color: #42b983;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 16px;
  transition: background 0.3s, transform 0.2s;
}

button:hover {
  background-color: #369e73;
  transform: scale(1.05);
}

button:disabled {
  background-color: #ccc;
  cursor: not-allowed;
}

.error {
  color: rgb(255, 80, 80);
  font-size: 12px;
  margin-top: 2px;
}

.success {
  color: #42b983;
  font-size: 14px;
  text-align: center;
  font-weight: bold;
  margin-top: 10px;
}
</style>
