<template>

<div id="container" class="main-container">
  <div class="logo">
    <img v-bind:src="image">
  </div>

</div>


</template>

<script>


</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');

*{
  font-size: 62.5%;
  box-sizing: border-box;
  font-family: 'Roboto', sans-serif;
  padding: 0;
  margin: 0;
}

.main-container {
  background-color: lightblue;
}

.main-title {
  font-size: 4rem;
  padding: 1rem;
  margin: 0;
}

</style>
