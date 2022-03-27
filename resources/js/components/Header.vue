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

</style>