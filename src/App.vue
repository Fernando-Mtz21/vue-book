<template>
  <div id="app">
    <IniciarSesion @toggleSesion="onToggleSesion" v-if="sesion.length == 0" />
    <div v-else>
      <h1>Hola Bart</h1>
      <CerrarSesion @logout="logginOut" />
      <Postear @posting="publicar" />
    </div>
  </div>
</template>

<script>
import IniciarSesion from './components/IniciarSesion.vue';
import CerrarSesion from './components/CerrarSesion.vue';
import Postear from './components/Postear.vue';

export default {
  name: 'App',
  components: {
    IniciarSesion,
    CerrarSesion,
    Postear,
  },
  data() {
    return {
      sesion: '',
      publicaciones: [],
    };
  },
  methods: {
    guardarRegistro() {
      console.log(sesion);
    },
    onToggleSesion(sesion) {
      this.sesion = sesion;
      console.log('Sesion nueva');
      console.log(this.sesion);
    },
    logginOut() {
      this.sesion = '';
    },
    publicar(publicacion) {
      this.publicaciones.push(publicacion);
      console.log(this.publicaciones);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
