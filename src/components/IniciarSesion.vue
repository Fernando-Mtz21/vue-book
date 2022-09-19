<template>
  <div>
    <form action="" v-on:submit.prevent="iniciarSesion">
      <input type="text" v-model="nombre" placeholder="Ingrese nombre" />
      <br />
      <input type="text" v-model="password" placeholder="Ingrese contraseña" />
      <br />
      <button type="submit">Guardar</button>
    </form>
  </div>
</template>
<script>
export default {
  name: 'IniciarSesion',
  data() {
    return {
      nombre: '',
      password: '',
    };
  },
  methods: {
    iniciarSesion() {
      console.log(this.nombre);
      console.log(this.password);
      this.$emit('toggleSesion', 1);
    },
  },
};
</script>
