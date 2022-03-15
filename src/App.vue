<template>
  <div id="app">
    <div class="container">
      <div class="row">
        <div class="col-12">
          <h1 class="mb-5">To Do List</h1>
        </div>
      </div>
      <div class="row justify-content-center">
        <div class="col-12">
          <h2>Crea una tarea</h2>
        </div>
        <div class="col-6">
          <div class="input-group mb-3">
            <input
              type="text"
              v-model="miTarea"
              class="form-control"
              placeholder=""
              aria-label="Example text with button addon"
              aria-describedby="button-addon1"
            />
            <button
              class="btn btn-outline-secondary"
              type="button"
              id="button-addon1"
              @click="agregarTarea"
            >
              Crear
            </button>
          </div>
        </div>
        <ul class="list-group list-group-flush">
          <h2>Tareas</h2>
          <li class="list-group-item my-2" v-for="(li, i) in lis" :key="i">
            {{ li }}
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      miTarea: "",
      lis: [],
    };
  },
  methods: {
    agregarTarea() {
      this.miTarea === ""
        ? alert("Por favor ingrese tarea")
        : this.lis.push(this.miTarea);
    },
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
