 <template>
  <div id="app" class="d-flex flex-column">
    <div class="align-self-center">
        <router-link class="Enlace" to="/">Home</router-link>
        <router-link class="mx-lg-2 Enlace" to="/signos">Agrupados por Elemento</router-link>
        <b-dropdown id="dropdown-1" text="Dropdown Button" class="m-md-2">
        <b-dropdown-item href="/?mes=1">Enero</b-dropdown-item>
        <b-dropdown-item href="/?mes=2">Febrero</b-dropdown-item>
        <b-dropdown-item href="/?mes=3">Marzo</b-dropdown-item>
        <b-dropdown-item href="/?mes=4">Abril</b-dropdown-item>
        <b-dropdown-item href="/?mes=5">Mayo</b-dropdown-item>
        <b-dropdown-item href="/?mes=6">Junio</b-dropdown-item>
        <b-dropdown-item href="/?mes=7">Julio</b-dropdown-item>
        <b-dropdown-item href="/?mes=8">Agosto</b-dropdown-item>
        <b-dropdown-item href="/?mes=9">Setiembre</b-dropdown-item>
        <b-dropdown-item href="/?mes=10">Octubre</b-dropdown-item>
        <b-dropdown-item href="/?mes=11">Noviembre</b-dropdown-item>
        <b-dropdown-item href="/?mes=12">Diciembre</b-dropdown-item>
  </b-dropdown>
    </div>
    <router-view />
  </div>
</template>

<script>

export default {
  name: "App",
  components: {
  },
  data() {
    return {
      zodiacos: [],
    };
  },
 mounted(){
    
    console.log('mounted')
  }
};
</script>
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
