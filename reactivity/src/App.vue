<template>
  <div id="app">
    <nav class="navbar">
      <img class="logo" src="./assets/totally not amazon dark logo.jpg">
      <div class="cart-button">
          <i class="fas fa-shopping-cart" v-on:click="myFilter" ></i>
        <ul id=dropDown class="shopping-list"> 
              <li id="list-title">Shopping List</li>
              <li>Link 1</li>
              <li>Link 2</li>
              <li>Link 2</li>
        </ul>
      </div>
    </nav>

    <div class="item-container">
      <div class="shopping-container">
       <div v-for="tech in technology" :key="tech.productId" class="shopping-card"> 
          <img class="shopping-image" :src="tech.productImage"> 
          <p class="shopping-name"> {{tech.productName}} </p>
        </div>
      </div>

      <div class="shopping-container">
        <div v-for="clothes in clothing" :key="clothes.productId" class="shopping-card">
          <img class="shopping-image" :src="clothes.productImage"> 
          <p class="shopping-name"> {{clothes.productName}} </p>
        </div>  
      </div>

      <div class="shopping-container">
        <div v-for="clothes in moreClothing" :key="clothes.productId" class="shopping-card">
          <img class="shopping-image" :src="clothes.productImage"> 
          <p class="shopping-name"  > {{clothes.productName}} </p>
        </div>  
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

    technology: [
      {
      productId: 1,
      productName: 'Keyboards',
      productImage: "https://images.unsplash.com/photo-1618384887929-16ec33fab9ef?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=880&q=80",
      },
      {
      productId: 2,
      productName: 'Monitors',
      productImage: "https://images.unsplash.com/photo-1527443224154-c4a3942d3acf?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80",
    },
    {
      productId: 3,
      productName: 'Smartphones',
      productImage: "https://images.unsplash.com/photo-1530319067432-f2a729c03db5?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1089&q=80",
    },
    ],

    clothing: [
    {
      productId: 4,
      productName: 'Jeans',
      productImage: "https://images.unsplash.com/photo-1624378440847-4a64ee1a889d?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1464&q=80",
    },
    {
      productId: 5,
      productName: 'T-shirts',
      productImage: "https://images.unsplash.com/photo-1620799139507-2a76f79a2f4d?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1072&q=80",
    },
    {
      productId: 6,
      productName: 'Sneakers',
      productImage: "https://images.unsplash.com/photo-1552346154-21d32810aba3?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1470&q=80",
    },
    ],

    moreClothing: [
    {
      productId: 7,
      productName: 'Sweater',
      productImage: "https://images.unsplash.com/photo-1620799140408-edc6dcb6d633?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1072&q=80",
    },
    {
      productId: 8,
      productName: 'Dress Shirt',
      productImage: "https://images.unsplash.com/photo-1603251578711-3290ca1a0187?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1470&q=80",
    },
    {
      productId: 9,
      productName: 'Denim Shorts',
      productImage: "https://images.unsplash.com/photo-1591195853828-11db59a44f6b?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1470&q=80",
    },
    ],
    isActive: false
  }
  },
  methods: {
    toggleList: function(event) { 
      let button = event.target
      button.classList.toggle("show");
    }
  }
}


</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400&display=swap');



* {
  font-size: 62.5%;
  box-sizing: border-box;
}

body{
  padding: 0;
  margin: 0;
}


.logo {
  width: 14rem;
}

.navbar {
  background-color: #0F1111;
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
  width: 100%;
  justify-content: space-evenly;

}

.shopping-container {
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  text-align: center;

}


.shopping-image {
  width: 100%;
  height: 100%;

}

.fa-shopping-cart {
  font-size: 3rem;
  color: white;
}

.shopping-name {
  margin: 1rem 0rem;
  font-family: 'Roboto', sans-serif;
  font-size: 2.5rem;
}

.cart-button {
  margin-right: 2rem;
  position: relative;
}

.shopping-list {
  display: none;
  position: absolute;
  background-color: #f1f1f1;
  min-width: 25rem;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  z-index: 1;
  right: 0.1rem;
  margin-top: 1rem;
}


.shopping-list li {
  color: black;
  padding: 1rem 0rem;
  text-decoration: none;
  display: flex;
  flex-direction: column;
  font-size: 2rem;
}

#list-title {
  color: black;
  font-weight: bold;
}

.show {display:block;}


</style>
