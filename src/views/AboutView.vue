<template>
  <div class="blog">
    <h1>Blog</h1>
    <button @click="listar">Listar</button>
    <button @click="agregar">Agregar</button>
    <button @click="borrar">borrar</button>
    <h1>{{informe}}</h1>
  </div>
</template>
<script>
import axios from 'axios'
export default {
  name:'Blog',
  data(){
    return{
      informe:[]
    }
  },  
  created(){
    this.informe= this.listar();
  },
  methods: {
    listar(){
      let config ={
        method: 'get',
        url: 'http://localhost:3000/post',
        headers: { }
      }
      axios(config)
      .then(response=>{
        this.informe=JSON.stringify(response.data)
      })
    },
    agregar(){
      let data = JSON.stringify({
        "name": "segundo post",
        "content": "Hola Mundo"
      });

      let config = {
        method: 'post',
        url: 'http://localhost:3000/post',
        headers: { 
          'Content-Type': 'application/json'
        },
        data : data
      };

      axios(config)
      .then(function (response) {
        console.log(JSON.stringify(response.data));
      })
    },
    borrar: function(result, id){
      let config = {
        method: 'delete',
        url: 'http://localhost:3000/post/8',
        headers: { }
      };

      axios(config)
      .then(function (response) {
        console.log(JSON.stringify(response.data));
      })
    }
  }
}
</script>
