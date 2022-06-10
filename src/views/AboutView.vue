<template>
  <div class="blog">
    <h1>Blog</h1>
    <button @click="listar">Listar</button>
    <button @click="agregar">Agregar</button>
    <h1>{{infor}}</h1>
  </div>
</template>
<script>
import axios from 'axios'
export default {
  name:'Blog',
  data(){
    return{
      response:'',
      infor:''
    }
  },
  methods: {
    listar(){
      let config ={
        method: 'get',
        url: 'http://localhost:3000/post',
        headers: { }
      }
      axios(config)
      .then(function (response) {
        console.log(JSON.stringify(response.data));
        this.infor=JSON.stringify(response.data);
      })
    },
    agregar(){
      let data = JSON.stringify({
        "name": "primer post",
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
    }
  }
}
</script>
