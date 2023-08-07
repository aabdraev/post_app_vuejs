<template>
    <div class="app">
        <h1>Posts page</h1>
        <my-button class="btn__create" @click="showDialog">Create post</my-button>
        <my-dialog v-model:show="dialogVisible">
            <post-form @create="createPost" />
        </my-dialog>
        <post-list :posts="posts" @remove="removePost" />
    </div>
</template>

<script>
import PostForm from "@/components/PostForm"
import PostList from "@/components/PostList"

export default {
    components: {
        PostForm, PostList
    },
    data() {
        return {
            posts: [
                { id: 1, title: "JS", body: " Desc" },
                { id: 2, title: "JS 2", body: " Desc 2" },
                { id: 3, title: "JS 3", body: " Desc 3" },
                { id: 4, title: "JS 4", body: " Desc 4" },
            ],
            dialogVisible: false,
        }
    },
    methods: {
        createPost(post) {
            this.posts.push(post)
            this.dialogVisible = false
        },
        removePost(post) {
            this.posts = this.posts.filter(p => p.id !== post.id)
        },
        showDialog() {
            this.dialogVisible = true
        },
        async fetchPosts() {

        }
    }
}
</script>

<style>
* {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}

.app {
    padding: 20px;
}

.btn__create {
    margin: 15px 0;
}
</style>