<template>
  <h2>Tipo de cuenta: {{cuenta}}</h2>
  <h2>Saldo: {{saldo}}</h2>
  <h2>Cuenta {{estado?'Activa':'Desactivada'}}</h2>
  <div v-for="(item,index) in servicios" :key="index">
    {{index+1}}-{{ item }}
  </div>
  <AccionSaldo
      @accion="aumentar"
      texto="Aumentar Saldo"/>
  <AccionSaldo
      @accion="disminuir"
      :desactivar="desactivar"
      texto="Disminuir Saldo"/>
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
      servicios:['giro','abono','transferencia'],
      desactivar:false
    }
  },
  methods:{
    aumentar(){
      this.desactivar=false
      if (this.saldo==1000){
        this.desactivar=true
        return
      }
      this.saldo = this.saldo+100
    },
    disminuir(){
      this.desactivar=false
      if (this.saldo==0){
        this.desactivar=true
        return
      }
      this.saldo = this.saldo-100
    }
  }
}

</script>

<style>

</style>