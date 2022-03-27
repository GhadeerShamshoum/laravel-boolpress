<template>
   <div>
        <div v-for="(post, index) in posts" :key="index">
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
    name: "SinglePost",
    data(){
        return {
            post: {},
        };
    },
    created() {
        axios
        .get(`/api/posts/${this.$route.params.slug}`)
        .then((response)=>{
            this.post = response.data
        }).catch ( (error) =>{
            // handle error
            this.$router.push({name: 'page-404'});
        })
    }
}
</script>

<style lang="scss" scoped>

</style>