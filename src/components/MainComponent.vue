<template>
    <div class="main-component">
      <slot name="header"></slot>
      <intermediate-component @data-emitted="handleDataEmitted" @loading="handleLoading"></intermediate-component>
      <p v-if="loading">Loading...</p>
      <p v-if="dataFromLeaf">Data from LeafComponent: <strong>{{ dataFromLeaf }}</strong></p>
      <button v-if="dataFromLeaf" @click="clearData">Kembali</button>
      <slot name="footer"></slot>
    </div>
  </template>
  
  <script>
  import IntermediateComponent from './IntermediateComponent.vue';
  
  export default {
    name: 'MainComponent',
    components: {
      IntermediateComponent
    },
    data() {
      return {
        dataFromLeaf: '',
        loading: false
      };
    },
    methods: {
      handleDataEmitted(data) {
        this.dataFromLeaf = data;
        this.loading = false;
      },
      handleLoading(isLoading) {
        this.loading = isLoading;
      },
      clearData() {
        this.dataFromLeaf = '';
      }
    }
  };
  </script>
  
  <style scoped>
  .main-component {
    border: 2px solid #3498db;
    padding: 20px;
    border-radius: 10px;
    background-color: #ecf0f1;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    max-width: 600px;
    margin: 0 auto;
  }
  h1 {
    color: #2980b9;
    font-family: 'Helvetica Neue', sans-serif;
  }
  p {
    font-size: 1.2em;
    color: #34495e;
  }
  button {
    background-color: #3498db;
    color: white;
    border: none;
    padding: 10px 20px;
    border-radius: 5px;
    cursor: pointer;
    font-family: 'Helvetica Neue', sans-serif;
    font-size: 1em;
    transition: background-color 0.3s ease;
    margin-top: 20px;
  }
  button:hover {
    background-color: #2980b9;
  }
  </style>
  