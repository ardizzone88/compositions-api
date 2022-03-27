<template>
  <div>
    {{ text }}
  </div>
  <div>{{ algo }}</div>
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
// mixins
import base from "@/mixins/base.js";

export default {
  name: "App",
  mixins: [base],
  components: {
    HomeVue,
    ModalVue,
  },
  data() {
    return {
      show: false,
    };
  },
  // Hooks
  beforeCreate() {
    console.log("beforeCreate", this.$data, this.$el);
  },
  created() {
    console.log("created", this.$data, this.$el);
  },
  mounted() {
    console.log("mounted", this.$data, this.$el);
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
