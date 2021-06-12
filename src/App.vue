<template>
  <div id="app" class="d-flex flex-column">
    <div class="align-self-center">
        <router-link class="Enlace" to="/">Home</router-link>
        <router-link class="mx-lg-2 Enlace" to="/signos">Agrupados por Elemento</router-link>
        <select>
          <option default disabled>-Seleccione un mes-</option>
          <option value="1">Enero</option>
          <option value="2">Febrero</option>
          <option value="3">Marzo</option>
          <option value="4">Abril</option>
          <option value="5">Mayo</option>
          <option value="6">Junio</option>
          <option value="7">Julio</option>
          <option value="8">Agosto</option>
          <option value="9">Septiembre</option>
          <option value="10">Octubre</option>
          <option value="11">Noviembre</option>
          <option value="12">Diciembre</option>
        </select>
    </div>
    <router-view />
  </div>
</template>

<style scoped>
.Enlace{
  color: grey;
  text-decoration: none;
  transition: color 0.5s;
}

.Enlace:hover{
  color: black;
}
</style>
