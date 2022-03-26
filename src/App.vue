<template>
  <button @click="show = !show">Menú</button>
<!-- Transicions in components -->
  <transition name="fade">
    <HomeVue v-show="show" />
  </transition>
  <div>
    <ModalVue v-show="show" />
  </div>
</template>

<script>
import HomeVue from "./components/HomeVue.vue";
import ModalVue from "./components/ModalVue.vue";
export default {
  name: "App",
  components: {
    HomeVue,
    ModalVue,
  },
  data() {
    return {
      show: false,
    };
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
/* opacidad ent transitions */
.fade-leave-to {
  opacity: 0;
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
  border: 1px solid red;
}
</style>
