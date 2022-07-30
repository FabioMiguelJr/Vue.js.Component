<template>
  <global-component></global-component>
  <local-component :title="title" @addclick="count += $event">
    <!-- Slot Test -->
    <template v-slot:header> Slot Header </template>
    <template v-slot:content> Slot Content </template>
  </local-component>
  <p>Count: {{ count }}</p>
</template>

<script>
import LocalComponent from "./components/LocalComponent.vue";

export default {
  data() {
    return {
      title: "Component Title",
      // Pode usar também: Number, Object, Boolean, Array, Function
      count: 0,
    };
  },
  computed: {
    computedTitle() {
      return "Teste " + this.title;
    },
  },
  methods: {},
  components: {
    LocalComponent,
  },

  // Ganchos de inicialização
  beforeCreate() {
    console.log("Before Create", this.title, this.computedTitle);
  },
  created() {
    console.log("Created", this.title, this.computedTitle);
  },

  // Ganchos de montagem (inserção no DOM)
  beforeMount() {
    console.log("Before mount");
  },
  mounted() {
    console.log("Mounted");
  },

  // Ganchos de atualização
  beforeUpdate() {
    console.log("Before Update");
  },
  updated() {
    console.log("Updated");
  },

  // Ganchos de destruição
  beforeUnmount() {
    console.log("Before Unmount");
  },

  unmounted() {
    console.log("Unmounted");
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
