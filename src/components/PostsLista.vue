<template>
    <div>
        
        <h2 class="m-5 text-center">Lista de posts</h2>

        <PostsListaIten
            v-for="post in posts" 
            :key="post.id"
            :post="post">
                <slot :meuPost="post"></slot>
        </PostsListaIten>
    </div>
</template>


<script>
import PostsListaIten from './PostListaIten.vue'
export default {
    components: {
        PostsListaIten
    },
    props: {
        posts: {
            type: Array,
            required: true
        }
    }
}
</script>