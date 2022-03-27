<template>
   <div>
        <div v-for="post in posts" :key="post.slug" class="post">
            <h1>{{post.title}}</h1>
            <div>
                <img v-if="post.image" :src="`/storage/${post.image}`" alt="post.title">
            </div>
            <h3>{{post.content}}</h3>
            <!-- cateegory -->
            <div v-if="post.category" class="category">{{post.category.name}}</div>
            <!-- tags -->
            <ul class="tags">
            <li v-for="tag in post.tags" :key="tag.slug" class="tag">{{tag.name}}</li>
            </ul>
        </div>
   </div>
    
</template>

<script>
export default{
    name: "Posts",
    data(){
        return {
            posts: [],
        };
    },
    created() {
        axios
        .get("/api/posts")
        .then((response)=>{
            this.posts = response.data
        })
    }
}
</script>

<style lang="scss" scoped>

</style>