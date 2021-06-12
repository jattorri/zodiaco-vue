<template>
  <div class="d-flex flex-wrap col-lg-10 mx-auto my-lg-5">
    <detalle-signo
      v-for="zodiaco in zodiacos"
      :key="zodiaco.id"
      :id="zodiaco.id"
      :imagen="zodiaco.imagen"
      :signo="zodiaco.signo"
      :elemento="zodiaco.elemento"
      :descripcion="zodiaco.descripcion"
    />
  </div>
</template>

<script>
import axios from "axios";
import DetalleSigno from "../components/DetalleSigno.vue";
export default {
  name: "Home",
  components: {
    "detalle-signo": DetalleSigno,
  },
  data() {
    return {
      zodiacos: [],
    };
  },
  methods: {
    async getZodiaco() {
      try {
        let data = await axios.get(
          "http://localhost:8080/test/tb/zodiaco.json"
        );
        this.zodiacos = data.data;
        console.log(this.$route.params.id);
      } catch (error) {
        console.error(error);
      }
    },
  },
  mounted() {
    this.getZodiaco();
  },
};
</script>

<style>
#app {
  height: 100vh;
}
</style>
