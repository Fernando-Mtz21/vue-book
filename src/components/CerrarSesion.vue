<template>
  <div>
    <button v-on:click="cerrarSesion">Cerrar Sesión</button>
  </div>
</template>
<script>
export default {
  name: 'CerrarSesion',
  methods: {
    cerrarSesion() {
      this.$emit('logout', '');
    },
  },
};
</script>
