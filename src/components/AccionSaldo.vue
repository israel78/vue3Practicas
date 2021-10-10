<template>
  <!--los atributos dinámicos siempre con dos puntos antes del nombre de la propiedad  :disabled?=-->
  <button :disabled="desactivar" @click="accion">{{texto}}</button>
</template>

<script>
export default {
  props:{
    texto:String,
    desactivar:Boolean
  },
  methods:{
    accion(){
      //se activa el metodo del componente padre "cuenta"
      this.$emit('accion')
    }
  }
}
</script>

<style>

</style>