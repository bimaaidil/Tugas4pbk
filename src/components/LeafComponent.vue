<template>
    <div class="leaf-component">
      <h3>Leaf Component</h3>
      <button @click="sendData" :disabled="loading">Send Data to Main</button>
    </div>
  </template>
  
  <script>
  export default {
    name: 'LeafComponent',
    data() {
      return {
        loading: false
      };
    },
    methods: {
      sendData() {
        this.loading = true;
        this.$emit('loading', true);
  
        // Simulate data sending with a timeout
        setTimeout(() => {
          const data = 'Hello from LeafComponent';
          this.$emit('leaf-data', data);
          this.loading = false;
          this.$emit('loading', false);
        }, 2000);
      }
    }
  };
  </script>
  
  <style scoped>
  .leaf-component {
    border: 2px solid #e74c3c;
    padding: 20px;
    border-radius: 10px;
    background-color: #fde3e3;
    margin-top: 20px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  }
  h3 {
    color: #c0392b;
    font-family: 'Helvetica Neue', sans-serif;
  }
  button {
    background-color: #e74c3c;
    color: white;
    border: none;
    padding: 10px 20px;
    border-radius: 5px;
    cursor: pointer;
    font-family: 'Helvetica Neue', sans-serif;
    font-size: 1em;
    transition: background-color 0.3s ease;
  }
  button:disabled {
    background-color: #c0392b;
    cursor: not-allowed;
  }
  button:hover:not(:disabled) {
    background-color: #c0392b;
  }
  </style>
  