<template>
    <div class="container">
        <div class="post">
            <h1>{{post.title}}</h1>
            <div class="imgContainer">
                <img v-if="post.image" :src="`/storage/${post.image}`" alt="post.title">
            </div>
            <div class="textContainer">
                <div v-if="post.content" class="content">{{post.content}}</div>
                <!-- cateegory -->
                <div v-if="post.category" class="category">{{post.category.name}}</div>
                <!-- tags -->
                <ul class="tags">
                <li v-for="tag in post.tags" :key="tag.slug" class="tag">#{{tag.name}}</li>
                </ul>
                <router-link :to="{ name: 'home'}">Back</router-link>
            </div>
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
.container{
    background-color: white;
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    .post{
        width: 1000px;
        h1{
            text-align: center;
        }
        .imgContainer{
            width: 600px;
            margin: auto;
            img{
                width: 100%;
            }

        }
        .textContainer{
            width: 600px;
            margin:10px auto;
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
        }
    }
}

</style>