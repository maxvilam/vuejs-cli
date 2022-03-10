<template>
  <div id="style">
    <h1 class="display-2 my-3 opacity-50">Crea una nueva tarea</h1>
    <p class="my-3"> 
    <span class="blockquote mx-1">Tarea</span>
    <input v-model="nombre" type="text" />
    <button @click="Guardar" class="btn btn-info mx-1">Crear</button>
    </p>
    <h2>Lista</h2>
    <ul class="centrarlista" v-for="(resultado, i) of arrayTarea" :key="i">
      <li class="justify-content-center">{{ 1 + i }}: {{ resultado.nombre }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      arrayTarea: [],
      nombre: "",
    };
  },
  methods: {
    Guardar() {
      if (!this.nombre) return;
      const unatarea = { nombre: this.nombre };
      this.arrayTarea.push(unatarea);
      console.log(this.arrayTarea);
      this.nombre = "";
    },
  },
};
</script>

<style lang="scss">
#style {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.centrarlista{
  display: flex;
  justify-content: center;
}
</style>
