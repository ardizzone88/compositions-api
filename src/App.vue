<template>
  <button @click="show = !show">Menú</button>
  <transition name="fade">
    <HomeVue v-show="show" />
  </transition>
</template>

<script>
import HomeVue from "./components/HomeVue.vue";
export default {
  name: "App",
  components: {
    HomeVue,
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
.fade-leave-to {
  opacity: 0;
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
  border: 1px solid red;
}
</style>
