<template>
  <main>
    <router-view :key="$route.path"></router-view>
  </main>
</template>

<script>

export default {
    name: "Main",

  

    
}
</script>

<style scoped>
main{
  margin-top: 90px;
  display: flex;
  justify-content: center;
}

</style>