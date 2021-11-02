<template>
  <div id="app">
    <nav class="navbar">
      <img class="logo" src="./assets/amazon.jpg">
      <div class="search-container">
          <input type="text" id="search-area" placeholder="">
            <button id="submit-button" type="submit">
                <i class="fa fa-search"></i>
            </button>
      </div>


      <div class="cart-button">
          <div class="cart-items">
              <p class="cart-items-value">{{shoppingItems.length}}</p>
          </div>
          <i class="fas fa-shopping-cart" @click="toggle"></i>
          <ul class="shopping-list" v-if="active"> 
                <li id="list-title">Shopping List</li>
                <li v-for="(shop, index) in shoppingItems" :key="shop.productName">{{shoppingItems[(index)]}}</li>
          </ul>
      </div>
    </nav>

    <div class="item-container">
      <div class="shopping-container">
       <div v-for="tech in technology" :key="tech.productName" class="shopping-card"> 
          <img class="shopping-container-image" :src="tech.productImage"> 
          <p class="shopping-container-name"> {{tech.productName}} </p>
          <button @click="cartArray(tech)" class="addCart">{{button}}</button>
        </div>
      </div>

      <div class="shopping-container">
        <div v-for="clothes in clothing" :key="clothes.productName" class="shopping-card">
          <img class="shopping-container-image" :src="clothes.productImage"> 
          <p class="shopping-container-name"> {{clothes.productName}} </p>
          <button @click="cartArray1(clothes)" class="addCart">{{button}}</button>
        </div>  
      </div>

      <div class="shopping-container">
        <div v-for="clothes in moreClothing" :key="clothes.productName" class="shopping-card">
          <img class="shopping-container-image" :src="clothes.productImage"> 
          <p class="shopping-container-name"  > {{clothes.productName}} </p>
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
      productName: 'Keyboard',
      productImage: "https://images.unsplash.com/photo-1618384887929-16ec33fab9ef?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=880&q=80",
      },
      {
      productId: 2,
      productName: 'Monitor',
      productImage: "https://images.unsplash.com/photo-1527443224154-c4a3942d3acf?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80",
    },
    {
      productId: 3,
      productName: 'Smartphone',
      productImage: "https://images.unsplash.com/photo-1530319067432-f2a729c03db5?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1089&q=80",
    },
    {
      productId: 4,
      productName: 'Laptop',
      productImage: "https://images.unsplash.com/photo-1496181133206-80ce9b88a853?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1171&q=80",
    },
    ],

    clothing: [
    {
      productId: 5,
      productName: 'Jeans',
      productImage: "https://images.unsplash.com/photo-1624378440847-4a64ee1a889d?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1464&q=80",
    },
    {
      productId: 6,
      productName: 'T-shirt',
      productImage: "https://images.unsplash.com/photo-1620799139507-2a76f79a2f4d?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1072&q=80",
    },
    {
      productId: 7,
      productName: 'Sneakers',
      productImage: "https://images.unsplash.com/photo-1552346154-21d32810aba3?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1470&q=80",
    },
    {
      productId: 8,
      productName: 'Glasses',
      productImage: "https://images.unsplash.com/photo-1572635196237-14b3f281503f?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=880&q=80",
    },
    ],

    moreClothing: [
    {
      productId: 9,
      productName: 'Sweater',
      productImage: "https://images.unsplash.com/photo-1620799140408-edc6dcb6d633?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1072&q=80",
    },
    {
      productId: 10,
      productName: 'Dress Shirt',
      productImage: "https://images.unsplash.com/photo-1603251578711-3290ca1a0187?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1470&q=80",
    },
    {
      productId: 11,
      productName: 'Denim Shorts',
      productImage: "https://images.unsplash.com/photo-1591195853828-11db59a44f6b?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1470&q=80",
    },
        {
      productId: 12,
      productName: 'Puffer Jacket',
      productImage: "https://media.istockphoto.com/photos/male-coat-isolated-on-the-white-picture-id163208487?b=1&k=20&m=163208487&s=170667a&w=0&h=YyOFKwoWyLSVO-cXE3goQ4el6K8Cvs082gjmUSouvOQ="
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
  font-family: 'roboto', sans-serif;
}

body{
  padding: 0;
  margin: 0;
}


.logo {
  width: 14rem;
  padding: 0.5rem;
}

.navbar {
  background-color: #131921;
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
  height: 200vh;
  width: 100%;
  justify-content: space-evenly;

}

.shopping-container {
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  text-align: center;

}


.shopping-container-image {
  width: 100%;
  height: 100%;

}

.fa-shopping-cart {
  font-size: 3.5rem;
  color: white;
}

.fa-shopping-cart:hover{
  color: #9EA5A8;
}

.shopping-container-name {
  margin: 1rem 0rem;
  font-family: 'Roboto', sans-serif;
  font-size: 2.5rem;
}

.cart-button {
  margin-right: 3rem;
  position: relative;
}

.cart-items{
  position: absolute;
  right: -1rem;
  top: -0.8rem;
  width: 2rem;
  height: 2rem;
  border-radius: 1rem;
  background-color: orange;
  display: flex;
  align-items: center;
  justify-content: center;
}

.cart-items-value{
  font-size: 1.5rem;
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
}

.addCart:hover{
  background-color: #C07C00;
}


.search-container {
  display: flex;
}

#search-area {
  width: 50vw;
  height: 5vh;
  font-size: 2rem;
  padding-left: 1rem;
}

#submit-button{
  background-color: orange;
  
}

.fa-search {
  font-size: 2rem;
  padding: 0.65rem 0.2rem;
}




</style>
