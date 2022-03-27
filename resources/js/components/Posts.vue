<template>
   <div class="container">
        <div v-for="post in posts" :key="post.slug" class="post">
            <div class="imgContainer">
                <img v-if="post.image" :src="`/storage/${post.image}`" alt="post.title">
            </div>
            <div class="title"><strong>{{post.title}}</strong></div>
            <div>{{post.content}}</div>
            <!-- cateegory -->
            <div v-if="post.category" class="category">{{post.category.name}}</div>
            <!-- tags -->
            <ul class="tags">
            <li v-for="tag in post.tags" :key="tag.slug" class="tag">{{tag.name}}</li>
            </ul>
            <router-link :to="{ name: 'single-post', params: {slug: post.slug} }">Visualizza Post</router-link>
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
.container{
    width: 1300px;
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    
    .post{
        background-color: white;
        width: 350px;
        margin: 10px;
        padding: 10px;
        .title{
            font-size: 22px;
        }
        .imgContainer{
            width: 100%;
            img{
                width: 100%;
            }
        }
    }
}

</style>