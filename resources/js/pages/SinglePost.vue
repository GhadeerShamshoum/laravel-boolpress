<template>
    <div class="container">
        <div class="post">
            <div>{{post.title}}</div>
            <div class="imgContainer">
                <img v-if="post.image" :src="`/storage/${post.image}`" alt="post.title">
            </div>
            <div v-if="post.content" class="content">{{post.content}}</div>
            <!-- cateegory -->
            <div v-if="post.category" class="category">{{post.category.name}}</div>
            <!-- tags -->
            <ul class="tags">
            <li v-for="tag in post.tags" :key="tag.slug" class="tag">{{tag.name}}</li>
            </ul>
            <li><router-link :to="{ name: 'home'}">Back</router-link></li>
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