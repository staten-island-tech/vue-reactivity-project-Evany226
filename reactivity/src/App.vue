<template>
  <div id="app">
    <nav class="navbar">
      <img class="logo" src="./assets/totally not amazon.jpg">
      <div class="cart-button">
        <img class="cart-button-icon" src="./assets/shopping cart.png">
      </div>
    </nav>

    <div class="item-container">
      <div class="shopping-container">
        <div class="shopping-card" :key="products.productId">
          <img :src="productImage">
        </div>
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
      products: ["Keyboards", "Monitors", "Smartphones", "Jeans", "T-Shirts", "Sweater", "Jacket", "Sneakers", "Sweatpants"],
      images: ["./assets/keyboard.jpg", "./assets.monitor.jpg", "./assets/smartphone.jpg"]
  }
  },
  products: [
    {
      productId: 1,
      productName: 'Keyboards',
      productImage: "./assets/keyboard.jpg",
    },
    {
      productId: 2,
      productName: 'Monitors',
      productImage: "./assets/monitor.jfif",
    },
    {
      productId: 3,
      productName: 'Smartphones',
      productImage: "./assets/smartphone.jpg",
    },
    {
      productId: 4,
      productName: 'Jeans',
      productImage: "./assets/jeans.jpg",
    },
    {
      productId: 5,
      productName: 'T-shirts',
      productImage: "./assets/t-shirt.jpg",
    },
    {
      productId: 6,
      productName: 'Sneakers',
      productImage: "./assets/keyboard.jpg",
    },
  ]
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

.cart-button {
  margin-right: 2rem;

}

.cart-button-icon {
  width: 5rem;
  }





</style>
