<template>
  <div id="app">
    <nav class="navbar">
      <img class="logo" src="./assets/totally not amazon.jpg">
      <div class="shopping-cart">
        <img class="shopping-cart-icon" src="./assets/shopping cart.png">
      </div>
    </nav>

    <div class="item-container">
      <div class="shopping-container">
        <div class="shopping-card"></div>
        <div class="shopping-card"></div>
        <div class="shopping-card"></div>
      </div>


<!-- <div v-for="product in products" :key="product" class="shopping-card"></div> -->
      
      <div class="shopping-container">
        <div class="shopping-card"></div>
        <div class="shopping-card"></div>
        <div class="shopping-card"></div>
      </div>

      <div class="shopping-container">
        <div class="shopping-card"></div>
        <div class="shopping-card"></div>
        <div class="shopping-card"></div>
      </div> 
    </div> 

  </div>
</template>

<script>

export default {
  name: 'App',
  components: {
  },
  data() {
    return {
      products: ["Keyboard", "Monitor", "Smartphones", "Jeans", "T-Shirts", "Sweater", "Jacket", "Sneakers", "Sweatpants"]
  }
  }
}

</script>

<style>

* {
  font-size: 62.5%;
  box-sizing: border-box;
}

body{
  padding: 0;
  margin: 0;
}

.logo {
  width: 16rem;
  padding: 1rem;
}

.navbar {
  background-color: orange;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.shopping-card {
  background-color: darkorange;
  width: 20vw;
  height: 30vh;
}

.item-container {
  display: flex;
  height: 120vh;
  width: 100vw;
  justify-content: space-evenly;
}

.shopping-container {
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
}

.shopping-cart-icon {
  width: 5rem;
}




</style>
