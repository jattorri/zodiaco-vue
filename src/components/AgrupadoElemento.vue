<template>
    <table class="table col-lg-6 mx-auto">
      <thead>
        <tr>
          <th>ELEMENTO</th>
          <th>SIGNOS</th>
        </tr>
      </thead>
      <tbody>
      <tr v-for="(signos, index) in array" :key="index">
        <td v-for="(ele, ind) in signos" :key="ind">
            <b v-for="(i, c) in ele" :key="c">{{ele[c]}} </b>
        </td>
      </tr>
           
      </tbody>

    </table>

</template>

<script>
import axios from 'axios';
export default {
  name: "AgrupadoElemento", 
    components: {
   
  },
  data(){
    return{
      array: new Map()
    }
  },
        methods:{
          async getZodiaco(){
            try{       
                axios.get('http://localhost:8080/test/tb/zodiaco.json').then(
                  data => {
                    let zodiacos = data.data;   
                    let temparray = new Map()
                    zodiacos.map( z => {
                      if(temparray.get(z.elemento) === undefined){
                        temparray.set(z.elemento,[])
                      }
                      temparray.get(z.elemento).push(z.signo)
                    })
                    this.array = temparray;
                  }
                )
              }catch(error){
                  console.error(error)
              }
          }},mounted(){
    this.getZodiaco()
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
