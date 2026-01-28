<template>
  <div id="app" style="text-align: center; font-family: sans-serif; padding: 40px;">
    <h1>Hola, {{ nombre || 'extraño' }}!</h1>
    
    <input 
      v-model="nombre" 
      placeholder="Escribe tu nombre..."
      style="padding: 10px; font-size: 1.2rem;"
    />

    <p v-if="nombre.length > 5" style="color: green;">
      ¡Qué nombre tan largo y elegante tienes!
    </p>

    <br><br>
    <button @click="limpiarNombre">Borrar todo</button>
  </div>
</template>

<script setup>
import { ref } from 'vue'

// Definimos la variable reactiva
const nombre = ref('')

// Función para el botón
const limpiarNombre = () => {
  nombre.value = ''
}
</script>

<style scoped>
button {
  background-color: #42b983; /* El color verde oficial de Vue */
  color: white;
  border: none;
  padding: 10px 20px;
  cursor: pointer;
  border-radius: 5px;
}
</style>