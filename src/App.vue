<script setup>
import { ref, computed } from 'vue'; 


// const name = 'este texto irá del script al template usando {{}}';
// const styleColor = 'color: blue';
// const arrayColor = [ "Blue", "Red", "green"];
// const activo = true;
// const arrayFrutas = [ "🍍", "🍌", "🍉", "🍏", "🍑"];
// const frutas = [
//   {
//     name: 'mango',
//     price: '$7.00',
//     description: 'un mango'
//   },
//   {
//     name: 'banano',
//     price: '$2.00',
//     description: 'un banano'
//   },
//   {
//     name: 'limon',
//     price: '$5.00',
//     description: 'un limon'
//   },
// ]
// const frutas2 = [
//   {
//     name: 'mango',
//     price: '$7.00',
//     description: 'un mango',
//     stock: 10
//   },
//   {
//     name: 'banano',
//     price: '$2.00',
//     description: 'un banano',
//     stock: 20
//   },
//   {
//     name: 'limon',
//     price: '$5.00',
//     description: 'un limon',
//     stock: 20
//   },
// ]
// const guitars = {
//   brand: 'gibson',
//   price : 1000,
//   color: 'black'
// }

// //metodo- methods
// const handleClick = (message) => {
//   console.log(message);
// }


const counter = ref(0);

const increment = () => {
  counter.value++};
const decrement = () => {
  
  counter.value--};
const restore = () => {
   counter.value = 0};

const classCounter = computed (() => {

  if ( counter.value > 0) {
    return 'positive'
  }
  if ( counter.value < 0) {
    return 'negative'
  }
  if ( counter.value === 0) {
    return 'zero'
  }
  
})

const  favNumbers = ref([]);

const addNum = () => {
  
  if (favNumbers != null ) {
   favNumbers.value.push(counter.value)
    console.log(`favNumbers ${favNumbers}`);
  }
}

const desactivar = computed (() => {

  const numSearch = favNumbers.value.find(num => num === counter.value)
  console.log(numSearch);
  if (numSearch === 0) {
    return true
  }
  return numSearch ? true : false;
})

</script>



<template>
  
    
  <!-- usando la interpolacion -->
  <!-- <h1>Hola {{name.toUpperCase()}}</h1>  -->
<!-- ---------------------------------------------------- -->

  <!-- usando el v-bind -->
  <!-- <h2 :style="styleColor"> usando el v-bind que es lo mismo que : </h2> -->
<!-- ---------------------------------------------------- -->


  <!-- interpretar algo en texto -->
  <!-- <h2>{{ arrayColor }}</h2> -->
<!-- ---------------------------------------------------- -->


  <!-- usando el v-bind -->
  <!-- <h2 :style="`color : ${arrayColor[2]}`">Soy verde</h2> -->
<!-- ---------------------------------------------------- -->


<!-- usando l v-if -->
    <!-- <p v-if="activo === true"><span> Estoy activo</span></p>
    <p v-else-if="activo === false"><span>Estoy inactivo</span></p>
    <p v-else><span>Estoy indeciso</span></p> -->
<!-- ---------------------------------------------------- -->


    <!-- usando v-for -->
    <!-- <ul>
       <li v-for="(frutas, index) of arrayFrutas"
       :key="index">
         {{ index }} - {{ frutas }}
       </li>
    </ul>
    <br>  -->
<!-- ---------------------------------------------------- -->


<!-- ejemplo 2  de for-->
    <!-- <ul>
        <li v-for=" fruta in frutas" :key="fruta.name">
        {{ fruta.name }} - {{ fruta.price }} - {{ fruta.description }}
        </li>
    </ul>
    <br> -->
<!-- ---------------------------------------------------- -->


<!-- ejemplo 3 de for -->
    <!-- <ul>
      <li v-for="guitar, key, index in guitars"> 
      {{index}} - {{ key }} : {{ guitar }}
      </li>
    </ul>
    <br> -->
<!-- ---------------------------------------------------- -->



<!-- ejemplo 4 de for usando el v-if-->
  <!-- <template v-for="fruta in frutas2" :key="fruta.name" >
    <li v-if="fruta.stock == 20">
        {{ fruta.name }} - {{ fruta.price }}
    </li>
  </template> -->
<!-- ---------------------------------------------------- -->

  

<!-- eventos  -->
<!-- <button v-on:click.left="handleClick('click Left')"> Activame left</button>
<button @click.middle="handleClick('Click Middle')"> Activame middle</button>
<button @click.right.prevent="handleClick('Click Right')"> Activame right</button> -->
<!-- ---------------------------------------------------- -->



<!-- usando el ref() -->

<!-- las clases pueden ser dinamicas -->


  <h2 :class="classCounter">{{counter}}</h2>
  
      
 

<button  @click="increment">Aumentar</button>
<button  @click="decrement">Disminuir</button>
<button  @click="restore">Restaurar</button>
<button  @click="addNum" :disabled="desactivar">Add</button>
<!-- ---------------------------------------------------- -->
<ul >
        <li await v-for="(number, index) in favNumbers" :key="index">
          {{index}} - {{number}}
        </li>
      </ul>

</template>

<style>
h1{
  color:red
}
.positive{
  color: green;
}

.negative{
  color: red;
}
.zero{
  color:blueviolet
}


</style>