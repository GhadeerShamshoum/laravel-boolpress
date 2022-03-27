<template>
   <div class="container">
        <div v-for="post in posts" :key="post.slug" class="post">
            <div v-if="post.image" class="imgContainer">
                <img :src="`/storage/${post.image}`" alt="post.title">
            </div>
            <div class="title"><strong>{{post.title}}</strong></div>
            <div>{{post.content}}</div>
            <!-- cateegory -->
            <div v-if="post.category" class="category"><span class="categoryName">{{post.category.name}}</span></div>
            <!-- tags -->
            <ul class="tags">
            <li v-for="tag in post.tags" :key="tag.slug" class="tag">#{{tag.name}}</li>
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
            margin: 10px 0;
        }
        .category{
            background-color: yellow;
            padding: 5px;
            width: 80px;
            margin: 10px 0;
            border-radius: 20px;
            text-align: center;
            .categoryName{
                font-weight: bold;
            }
        }
        .tags{
            list-style: none;
            margin: 10px 0;
            padding: 0;
            display: flex;
            .tag{
                padding: 5px;
                background-color: rgb(89, 182, 212);
                color: white;
                margin: 0 5px;
                border-radius: 5px;
                font-size: 10px;
                font-weight: bold;
            }
        }
        .imgContainer{
            width: 100%;
            height: 190px;
            overflow: hidden;
            img{
                width: 100%;
            }
        }
    }
}

</style>