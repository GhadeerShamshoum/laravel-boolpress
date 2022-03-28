<template>
  <header>
    <nav>
      <li><router-link :to="{ name: 'home'}">Home</router-link></li>
      <li><router-link :to="{ name: 'About'}">About us</router-link></li>
    </nav>
  </header>
</template>

<script>

export default {
    name: "Header",

    
}
</script>

<style lang="scss" scoped>
header{
  height: 90px;
  width: 100%;
  background-color: white;
  position: fixed;
  top: 0;
  nav{
    width: 90%;
    height: 100%;
    margin: auto;
    display: flex;
    li{
      height: 100%;
      line-height: 90px;
      margin: 0 10px;
      list-style: none;
      text-decoration: none;
    }
  


  }
}
</style>