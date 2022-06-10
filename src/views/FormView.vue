<template>
  <div class="form">
    <h1>Formulario</h1>
    <input v-model="message" placeholder="Ingrese su nombre">
    <button @click="cap">Mayus</button>
    <h1>{{message2}}</h1>
  <!-- <p>El mensaje es: {{ message }}</p> -->
  </div>
</template>
<script>
export default {
  name: 'Form',
  data(){
    return{
      message:'',
      message2:''
    }
  },
  methods:{
    cap: function(event){
      this.message2=this.message.toUpperCase();
    }
  }
}
</script>