<template>
  <global-component></global-component>
  <local-component :title="title" @addclick="count += $event"></local-component>
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
  methods: {},
  components: {
    LocalComponent,
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
