<script setup>
import { ref } from 'vue';


let tabla = ref(2)
let tablaInput
let operacionProhibido = ref(false)
let valorMuyAlto = ref(false)

const calcular = () =>{
  operacionProhibido.value = false
  valorMuyAlto.value = false
  tablaInput = +tablaInput

  if(tablaInput == 0){
    operacionProhibido.value = true
  }

  if(tablaInput < 0){
    tablaInput = tablaInput * -1
  }
  
  if( tablaInput >= 1 && tablaInput <= 100){
    tabla.value = tablaInput
  } else{
    valorMuyAlto.value = true
  }
  

}

</script>

<template>

  <div class="py-2 mt-12 w-80 shadow-md mx-auto rounded bg-sky-600">
    <div class="px-8 py-3">
      <input class="border rounded py-1/2 border-indigo-800" type="text" v-model="tablaInput"> <button class="bg-slate-400 px-1 py-1/2 rounded" @click="calcular">Calcular</button>
      <p v-show="operacionProhibido == true" class="text-red-600"> Operación prohibida</p>
      <p v-show="valorMuyAlto == true" class="text-yellow-500"> Un valor muy alto</p>
    </div>
    <div class="px-10 py-3">
      <ul class="px-16">
      <li class="text-white">{{ tabla }} x 1 = {{ tabla * 1 }} </li>
      <li class="text-white">{{ tabla }} x 2 = {{ tabla * 2 }} </li>
      <li class="text-white">{{ tabla }} x 3 = {{ tabla * 3 }} </li>
      <li class="text-white">{{ tabla }} x 4 = {{ tabla * 4 }} </li>
      <li class="text-white">{{ tabla }} x 5 = {{ tabla * 5 }} </li>
      <li class="text-white">{{ tabla }} x 6 = {{ tabla * 6 }} </li>
      <li class="text-white">{{ tabla }} x 7 = {{ tabla * 7 }} </li>
      <li class="text-white">{{ tabla }} x 8 = {{ tabla * 8 }} </li>
      <li class="text-white">{{ tabla }} x 9 = {{ tabla * 9 }} </li>
      <li class="text-white">{{ tabla }} x 10 = {{ tabla * 10 }} </li>
      </ul>
     
    </div>
  </div>

  
</template>


