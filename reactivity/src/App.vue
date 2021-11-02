<template>
  <div id="app">
    <nav class="navbar">
      <img class="logo" src="./assets/amazon.jpg">
      <div class="cart-button">
          <i class="fas fa-shopping-cart" @click="toggle"></i>
        <ul class="shopping-list" v-if="active"> 
              <li id="list-title">Shopping List</li>
              <li>{{shoppingItems}}</li>
        </ul>
      </div>
    </nav>

    <div class="item-container">
      <div class="shopping-container">
       <div v-for="tech in technology" :key="tech.productName" class="shopping-card"> 
          <img class="shopping-image" :src="tech.productImage"> 
          <p class="shopping-name"> {{tech.productName}} </p>
          <button @click="cartArray(tech)" class="addCart">{{button}}</button>
        </div>
      </div>

      <div class="shopping-container">
        <div v-for="clothes in clothing" :key="clothes.productName" class="shopping-card">
          <img class="shopping-image" :src="clothes.productImage"> 
          <p class="shopping-name"> {{clothes.productName}} </p>
          <button @click="cartArray1(clothes)" class="addCart">{{button}}</button>
        </div>  
      </div>

      <div class="shopping-container">
        <div v-for="clothes in moreClothing" :key="clothes.productName" class="shopping-card">
          <img class="shopping-image" :src="clothes.productImage"> 
          <p class="shopping-name"  > {{clothes.productName}} </p>
          <button @click="cartArray2(clothes)" class="addCart">{{button}}</button>
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
    button: 'Add to Cart',
    shoppingItems: [],
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
    active: false
  }
  },
  mounted: function(){
  },
  methods: {
    toggle() { 
      this.active = !this.active
    },

    cartArray(tech) {
      this.shoppingItems.push(tech.productName);
    },

    cartArray1(clothes) {
      this.shoppingItems.push(clothes.productName);
    },

    cartArray2(clothes) {
      this.shoppingItems.push(clothes.productName);
    },

    
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
  padding: 1rem;
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
  height: 140vh;
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
  font-size: 3.5rem;
  color: white;
}

.shopping-name {
  margin: 1rem 0rem;
  font-family: 'Roboto', sans-serif;
  font-size: 2.5rem;
}

.cart-button {
  margin-right: 3rem;
  position: relative;
}

.shopping-list {
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



.addCart {
  background-color: orange;
  font-size: 1.5rem;
  margin: 0rem;
  padding: 1rem 2.5rem;
  color: black;
  border-radius: 0.5rem;
  border: none;

<<<<<<< HEAD
}
=======

>>>>>>> parent of 929fc06 (added items in cart)


</style>
