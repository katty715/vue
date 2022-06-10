<template>
    <div class="home">
        <button class="btn" @click="cambiar">Cambiar</button>
        <div>
            <img :src="laimg" alt="">
        </div>
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
    border:2px solid;
}
.btn{
    background-color: #4CAF50; /* Green */
    border: none;
    color: white;
    padding: 15px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
}
</style>