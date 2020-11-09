<template>
    <section class="container my-5 py-2">
        <div class="row">
            <div class="col-12 col-sm-12 col-md-6 col-lg-4" v-for="(task, index) in nuevasTareas" :key="index">
                <div class="card">
                    <img src="https://static.t13.cl/images/original/2016/06/1467321308-prada2.gif" class="card-img-top p-3" :alt="task.id">
                    <div class="card-body">
                        <h5 class="card-title">{{task.tarea}}</h5>
                        <p class="card-text">{{task.descripcion}}</p>
                        <button type="button" class="btn btn-info">Eliminar</button>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>
<script>
export default {
    name: 'Cards',
    props: {
        nuevasTareas: {
            type: Array,
            required: true,
        }
    }
}
</script>
<style scoped>
</style>