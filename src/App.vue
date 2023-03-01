<script setup>
const name = 'este texto irá del script al template usando {{}}';
const styleColor = 'color: blue';
const arrayColor = [ "Blue", "Red", "green"];
const activo = true;
const arrayFrutas = [ "🍍", "🍌", "🍉", "🍏", "🍑"];
const frutas = [
  {
    name: 'mango',
    price: '$7.00',
    description: 'un mango'
  },
  {
    name: 'banano',
    price: '$2.00',
    description: 'un banano'
  },
  {
    name: 'limon',
    price: '$5.00',
    description: 'un limon'
  },
]
const frutas2 = [
  {
    name: 'mango',
    price: '$7.00',
    description: 'un mango',
    stock: 10
  },
  {
    name: 'banano',
    price: '$2.00',
    description: 'un banano',
    stock: 20
  },
  {
    name: 'limon',
    price: '$5.00',
    description: 'un limon',
    stock: 20
  },
]
const guitars = {
  brand: 'gibson',
  price : 1000,
  color: 'black'
}
</script>


<template>
  
    
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

    <br>
<!-- ejemplo 2  de for-->
    <ul>
        <li v-for=" fruta in frutas" :key="fruta.name">
        {{ fruta.name }} - {{ fruta.price }} - {{ fruta.description }}
        </li>
    </ul>
    <br>
<!-- ejemplo 3 de for -->
    <ul>
      <li v-for="guitar, key, index in guitars"> 
      {{index}} - {{ key }} : {{ guitar }}
      </li>
    </ul>

    <br>

<!-- ejemplo 4 de for usando el v-if-->
  <template v-for="fruta in frutas2" :key="fruta.name" >
    <li v-if="fruta.stock == 20">
        {{ fruta.name }} - {{ fruta.price }}
    </li>
  </template>

</template>

<style>
h1{
  color:red
}
</style>