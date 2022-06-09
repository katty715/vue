<template>
    <div class="home">
        <button @click="cambiar">Cambiar</button>
        <img :src="laimg" alt="">
        
    </div>
</template>
<script>
export default {
    name:'Home',
    props:{
        msg: String
    },
    data(){
        return{
            titulo: 'Home',
            estado: true,
            laimg: '',
            img1: 'https://img.freepik.com/vector-gratis/mano-sostiene-cartel-texto-yes-satisfaccion-aceptacion_100456-1882.jpg',
            img2: 'https://www.ccoo-servicios.es/imagenes/tic/2014-02-18_Comunicado_20_-_NO.png'
        }
    },
    mounted(){
        if (this.estado==true) {
            this.laimg = this.img1;
        } else {
            this.laimg = this.img2;
        }
    },
    methods:{
        cambiar() {
            if (this.estado) {
                this.estado=false;
                this.laimg=this.img2; 
            }else{
                this.estado=true;
                this.laimg=this.img1;
            }
                       
            console.log('cambiando estado');
        }
    }
}
</script>
<style>
img{
    max-width: 30%;
}
</style>