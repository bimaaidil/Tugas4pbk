<template>
  <div id="app">
    <main-component>
      <template #header>
        <h1>Custom Header from Parent</h1>
      </template>
      <template #footer>
        <p>Custom Footer from Parent</p>
      </template>
    </main-component>
  </div>
</template>

<script>
import MainComponent from './components/MainComponent.vue';

export default {
  name: 'App',
  components: {
    MainComponent
  }
};
</script>

<style>
#app {
  font-family: 'Arial', sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background-color: #f0f8ff;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
