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
    h1{
        text-transform: uppercase;
        color: #4095e0;
        font-size: 50px;
    }
}
</style>