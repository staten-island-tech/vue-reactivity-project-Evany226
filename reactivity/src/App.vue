<template>
  <div id="app">
    <nav class="navbar">
      <img class="logo" src="./assets/totally not amazon.jpg">
    </nav>

    <div class="item-container">
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
      products: ["Keyboard", "Mouse", "Jeans", "T-Shirts"]
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
}

.shopping-card {
  background-color: darkorange;
  width: 20vw;
  height: 25vh;
  padding: 2rem;
}

.item-container {
  display: flex;
  height: 100vh;
  justify-content: space-evenly;
}

.shopping-container {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
}

</style>
