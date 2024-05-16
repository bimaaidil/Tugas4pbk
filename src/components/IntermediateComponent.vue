<template>
    <div class="intermediate-component">
      <h2>Intermediate Component</h2>
      <leaf-component @leaf-data="handleLeafData" @loading="handleLoading"></leaf-component>
    </div>
  </template>
  
  <script>
  import LeafComponent from './LeafComponent.vue';
  
  export default {
    name: 'IntermediateComponent',
    components: {
      LeafComponent
    },
    methods: {
      handleLeafData(data) {
        this.$emit('data-emitted', data);
      },
      handleLoading(isLoading) {
        this.$emit('loading', isLoading);
      }
    }
  };
  </script>
  
  <style scoped>
  .intermediate-component {
    border: 2px solid #2ecc71;
    padding: 20px;
    border-radius: 10px;
    background-color: #e8f8f5;
    margin-top: 20px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  }
  h2 {
    color: #27ae60;
    font-family: 'Helvetica Neue', sans-serif;
  }
  </style>
  