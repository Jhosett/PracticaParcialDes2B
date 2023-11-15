<script setup>
let listadoVehiculos=[
  {
    categoria:'automovil',
    tiempoEstadia:45,
    estaEnParqueadero:true,
  },
  {
    categoria:'motocicleta',
    tiempoEstadia:30,
    estaEnParqueadero:true,
  },
  {
    categoria:'pesado',
    tiempoEstadia:60,
    estaEnParqueadero:false,
  },
  {
    categoria:'automovil',
    tiempoEstadia:90,
    estaEnParqueadero:true,
  },
  {
    categoria:'motocicleta',
    tiempoEstadia:15,
    estaEnParqueadero:false,
  },
  {
    categoria:'motocicleta',
    tiempoEstadia:105,
    estaEnParqueadero:false,
  }
]


let variable={
  motocicleta: 1000,
  automovil: 2000,
  pesado: 3000,
}

let total = 0

function calcularTotal(categoria,tiempoEstadia) {
  total = (variable[categoria]*tiempoEstadia)/15
  return total
}


</script>

<template>
  <h1>Están en el parqueadero</h1>
  <div v-for="(obj, index) in listadoVehiculos" :key="index">
    <span v-if="obj.estaEnParqueadero">
      <h1>{{ obj.categoria }}</h1>
      <h1>{{ obj.tiempoEstadia }}</h1>
      <h1>{{ obj.estaEnParqueadero }}</h1>
    </span>
  </div>
  <h1>No están en el parqueadero</h1>
  <div v-for="(obj, index) in listadoVehiculos" :key="index">
    <span v-if="!obj.estaEnParqueadero">
      <h1>{{ obj.categoria }}</h1>
      <h1>{{ obj.tiempoEstadia }}</h1>
      <h1>{{ obj.estaEnParqueadero }}</h1>
      <span v-if="obj.categoria=='pesado'">
      <ul>{{ calcularTotal(obj.categoria,obj.tiempoEstadia) }}</ul>
    </span>
    <span v-if="obj.categoria=='automovil'">
      <ul>{{ calcularTotal(obj.categoria,obj.tiempoEstadia) }}</ul>
    </span>
    <span v-if="obj.categoria=='motocicleta'">
      <ul>{{ calcularTotal(obj.categoria,obj.tiempoEstadia) }}</ul>
    </span>
    </span>
  </div>
</template>

<style scoped>

</style>
