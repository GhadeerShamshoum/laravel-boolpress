<template>
  <header>
    <nav>
      <li><router-link class="link" :to="{ name: 'home'}">Home</router-link></li>
      <li><router-link class="link" :to="{ name: 'About'}">About us</router-link></li>
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
      line-height: 90px;
      margin: 0 20px;
      list-style: none;
      text-decoration: none;
      cursor: pointer;
        &:hover{
          border-bottom: 4px solid rgb(49, 166, 196);
        }
        &:hover .link{
          color: rgb(49, 166, 196);
        }
      .link{
        text-decoration: none;
        color:black;
        height: 100%;
        text-transform: uppercase;
        font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
        font-weight: 800;
      }
    }
  


  }
}
</style>