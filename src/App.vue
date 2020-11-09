<template>
  <div id="app">
    <Lista @enviandoInfo="ingresarTarea"/>
    <Cards :nuevasTareas="listaTareas"/>
  </div>
</template>

<script>
import Lista from './components/Lista.vue'
import Cards from './components/Cards.vue'

export default {
  name: 'App',
  components: {
    Lista,
    Cards,
  },
  data() {
    return {
      listaTareas: [],
    };
  },
  methods: {
    ingresarTarea(tarea) {
      console.log(tarea);
      this.listaTareas.push(tarea);
    },
    // eliminarTarea(index) {
    //   this.lista.splice(index, 1);
    // }
  },
}
</script>

<style>
body {
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
  background-color: #ffffff;
  color: #3d627a;
}
</style>
