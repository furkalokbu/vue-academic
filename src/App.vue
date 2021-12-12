<template>
    <div class="app">
        <post-form 
        @create="createPost"/>
        <post-list 
        v-bind:posts="posts"
        @remove="removePost"
        />
    </div>
</template>

<script>
import PostForm from "@/components/PostForm"
import PostList from "@/components/PostList"

export default {
    data()  {
        return {
            posts: [
                {id: 1, title: 'JavaScript', body: 'Describe post'},
                {id: 2, title: 'JavaScript 2', body: 'Describe post 2'},
                {id: 3, title: 'JavaScript 3', body: 'Describe post 3'},
            ],
    }
        },
    methods: {
        createPost(post) {
            this.posts.push(post);
        },
        removePost(post) {
            this.posts = this.posts.filter(p => p.id !== post.id )
        }
    },
    components: {
        PostList, PostForm
    }
}
</script>

<style>
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

.app {
   padding: 20px; 
}

</style>