<script setup>
// Constantes
const name = "Vue variable";
const arrayColors = ["blue", "red", "black"];
const arrayRaces = ["Blanca", "Mestiza", "Negra"];
const arrayCities = ["Colombiano", "Brasileño", "Argentino"];
const arrayLanguages = ["Español", "Ingles", "Portugues", "Mandarin"];

// Metodo
const handlerClickParam = (message) => {
  console.log(message);
};
const handlerClick = () => {
  console.log("Click");
};
</script>

<template>
  <div>
    <h1>Hola {{ name.toUpperCase() }}</h1>

    <h2>{{ arrayColors }}</h2>

    <h2 v-bind:style="`color:${arrayColors[2]}`">
      Soy {{ arrayCities[2] }} de raza {{ arrayRaces[1] }}
    </h2>

    <ul>
      <li v-for="(language, index) in arrayLanguages" :key="index">
        {{ index }}->{{ language }}
      </li>
    </ul>

    <button v-on:click="handlerClick">Activame</button>
    <button @click="handlerClickParam('Parametro')">Activame 2</button>
  </div>
</template>

<style>
h1 {
  color: red;
}
</style>
