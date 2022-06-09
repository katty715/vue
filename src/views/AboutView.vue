<template>
  <div class="blog">
    <h1>Blog</h1>
    <button @click="listar">Listar</button>
    <button @click="agregar">Agregar</button>
    <div id="prueba">
      {{info}}
    </div>
  </div>
</template>
<script>
import axios from 'axios'
export default {
  name:'Blog',
  data(){
    //let postC = {header:'Content-Type:aplication/json'};
    //let postC = {header:'Content-Type:aplication/json'};
    return{
      info:''
    }
  },
  methods: {
    listar(){
      let config ={
        method: 'get',
        url: 'http://localhost:3000/post',
      }
      axios(config)
      .then(response => (this.info = response.data))
      .catch(e=>{console.log(e);})
    },
    async agregar(){
      let config ={
        method: 'post',
        url: 'http://localhost:3000/post',
        data:{
          name: "primer post",
         content: "Hola Mundo"
        },
        headers:{'Content-Type':'aplication/json'}
      }
      let res = await axios(config)
      .then(response => (this.info = response)) 
      .catch(e=>{console.log(e);})
      console.log(res);
    }
  }
}
</script>
