<template>
    <div class="containerMain">
        <h1>Home Page</h1>
        <Posts/>
    </div>  
</template>

<script>
import Posts from '../components/Posts.vue'
export default{
    name: "Home",
    components:{
        Posts
    }
}
</script>

<style lang="scss" scoped>
.containerMain{
    display: flex;
    flex-direction: column;
    align-items: center;
}
</style>