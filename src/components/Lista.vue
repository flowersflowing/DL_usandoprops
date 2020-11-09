<template>
  <header class="lista">
    <h1 class="text-center m-4">Lista de tareas</h1>
    <hr>
    <form class="mt-5 mx-5" @submit.prevent="agregarTarea">
      <section class="container">
        <div class="my-2">
          <label class="mx-3" for="tarea">Nueva tarea:</label>
          <input class="form-control" type="text" v-model="tarea">        
        </div>        
        <div class="my-2">
          <label class="mx-3" for="descripcion">Descripción:</label>
          <input class="form-control" type="text" v-model="descripcion">        
        </div>
        <div class="text-center mt-4">
          <button class="btn btn-dark" type="submit">Agregar</button>
          <button class="btn btn-outline-dark" type="reset">Limpiar</button>              
        </div>
      </section>
    </form>
  </header>
</template>

<script>
export default {
  name: 'Lista',
  // vamos a usar emit aquí, porque le va a enviar información al padre
  data() {
    return {
      tarea: '',
      descripcion: '',
      id: 0,
    }
  },
  methods: {
    agregarTarea() {
      if (this.tarea && this.descripcion) {
        let infoTarea = {
          tarea: this.tarea,
          descripcion: this.descripcion,
          id: this.id++
        }
        this.$emit("enviandoInfo", infoTarea);
      }
      else {
        console.log("no hay datos");
      }
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  button {
    margin-left: 1em;
  }
  label {
    font-size: 1.3em;
  }
  .lista {
    background-color: #e3f4f5;
    padding-bottom: 4em;
    padding-top: 4em;
  }
</style>
