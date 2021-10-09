<template>
    <h2>Tipo de cuenta: {{cuenta}}</h2>
  <h2>Saldo: {{saldo}}</h2>
  <h2>Cuenta {{estado?'Activa':'Desactivada'}}</h2>
  <div v-for="(item,index) in servicios" :key="index">
      {{index+1}}-{{ item }}
  </div>
  <AccionSaldo texto="Aumentar Saldo"/>
  <AccionSaldo texto="Disminuir Saldo"/>
</template>

<script>
import AccionSaldo from './AccionSaldo.vue'
export default {
components:{
    AccionSaldo
},
 data() {
     return {
         saldo: 100,
         estado: true,
         cuenta: 'Visa',
         servicios:['giro','abono','transferencia']
     }
 },
     methods:{
         aumentar(){
             this.saldo = this.saldo+100
         },
         disminuir(){
            this.saldo = this.saldo-100
         }
     }
 }

</script>

<style>

</style>