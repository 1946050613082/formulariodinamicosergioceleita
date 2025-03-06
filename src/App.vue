<script setup>
import FormComponent from './components/FormComponent.vue';
import contacto from '@/assets/dfg.png'; // Importa correctamente la imagen
import { ref } from 'vue';

const isFormSubmitted = ref(false);

const handleFormSubmit = () => {
  isFormSubmitted.value = true;
  setTimeout(() => {
    isFormSubmitted.value = false;
  }, 3000); // Mensaje de confirmación desaparece después de 3 segundos
};
</script>

<template>
  <header class="header">
    <div class="container">
      <img :src="contacto" alt="Logo de la empresa" class="logo" />
      <h1 class="title">Formulario de Registro</h1>
      <p class="subtitle">Completa los campos y envía tu información.</p>
    </div>
  </header>

  <main class="main">
    <div class="form-wrapper">
      <FormComponent @submit="handleFormSubmit" />
      <div v-if="isFormSubmitted" class="confirmation-message">
        ¡Gracias por registrarte!
      </div>
    </div>
  </main>

  <button v-if="showScrollButton" class="scroll-to-top" @click="scrollToTop">
    ↑
  </button>
</template>

<style scoped>
/* Estilos generales mejorados */
.header {
  background: linear-gradient(135deg,rgba(76, 107, 175, 0.81),rgb(132, 129, 184));
  color: white;
  padding: 40px 20px;
  text-align: center;
  border-radius: 0 0 20px 20px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
}

.container {
  max-width: 600px;
  margin: auto;
}

.logo {
  width: 120px;
  height: auto;
  margin-bottom: 15px;
  animation: fadeIn 1s ease-in-out;
}

.title {
  font-size: 2.2rem;
  font-weight: bold;
  margin-bottom: 10px;
}

.subtitle {
  font-size: 1.1rem;
  opacity: 0.9;
}

/* Mejorando la presentación del formulario */
.main {
  display: flex;
  justify-content: center;
  margin-top: 30px;
  padding: 20px;
}

.form-wrapper {
  background: white;
  padding: 30px;
  border-radius: 12px;
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.15);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  max-width: 500px;
  width: 100%;
}

.form-wrapper:hover {
  transform: translateY(-5px);
  box-shadow: 0 12px 24px rgba(0, 0, 0, 0.2);
}

.confirmation-message {
  margin-top: 20px;
  padding: 10px;
  background:rgb(172, 169, 207);
  color: white;
  text-align: center;
  border-radius: 5px;
  animation: fadeIn 0.5s ease-in-out;
}

.scroll-to-top {
  position: fixed;
  bottom: 20px;
  right: 20px;
  background:rgba(130, 122, 160, 0.66);
  color: white;
  border: none;
  border-radius: 50%;
  width: 50px;
  height: 50px;
  font-size: 1.5rem;
  cursor: pointer;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
  transition: background 0.3s ease;
}

.scroll-to-top:hover {
  background: #2e7d32;
}

/* Animaciones */
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(-10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@media (min-width: 1024px) {
  .header {
    padding: 50px;
  }

  .title {
    font-size: 2.5rem;
  }

  .subtitle {
    font-size: 1.2rem;
  }
}

@media (max-width: 768px) {
  .header {
    padding: 30px 20px;
  }

  .title {
    font-size: 2rem;
  }

  .subtitle {
    font-size: 1rem;
  }

  .form-wrapper {
    padding: 20px;
  }
}
</style>