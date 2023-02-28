<script setup>
const name = 'este texto irá del script al template usando {{}}';
const styleColor = 'color: blue';
const arrayColor = [ "Blue", "Red", "green"];
const activo = true;
const arrayFrutas = [ "🍍", "🍌", "🍉", "🍏", "🍑"];
</script>


<template>
  <div>
    
  <!-- usando la interpolacion -->
  <h1>Hola {{name.toUpperCase()}}</h1> 
  <!-- usando el v-bind -->
  <h2 :style="styleColor"> usando el v-bind que es lo mismo que : </h2>
  <!-- interpretar algo en texto -->
  <h2>{{ arrayColor }}</h2>
  <!-- usando el v-bind -->
  <h2 :style="`color : ${arrayColor[2]}`">Soy verde</h2>
<!-- usando l v-if -->
    <p v-if="activo === true"><span> Estoy activo</span></p>
    <p v-else-if="activo === false"><span>Estoy inactivo</span></p>
    <p v-else><span>Estoy indeciso</span></p>
    <!-- usando v-for -->
    <ul>
       <li v-for="(frutas, index) in arrayFrutas"
       :key="index">
         {{ index }} - {{ frutas }}
       </li>
    </ul>
  </div>
</template>

<style>
h1{
  color:red
}
</style>