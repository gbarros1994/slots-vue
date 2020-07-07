<template>
  <div id="app" class="container">
    
    <h1>Forma padrão</h1>
    <PostsLista :posts="posts"/>

    <h1>Slot com scopo</h1>
    <PostsLista :posts="posts">
      <template slot-scope="slotProps">
        <h2>{{ slotProps.meuPost.titulo }}</h2>
        <p>{{ slotProps.meuPost.conteudo }}</p>
        <small>{{ slotProps.meuPost.autor }}</small>
      </template>
    </PostsLista>

  </div>
</template>

<script>
import PostsLista from './components/PostsLista.vue'
export default {
  components: {
    PostsLista
  },
  data() {
    return {
      posts: [
        { id: 1, titulo: 'Components no Vue', conteudo: 'Componetens são legais', autor: 'Gerson'},
        { id: 2, titulo: 'Components no Vue', conteudo: 'Componetens são legais', autor: 'Carlos'}
      ]
    }
  },
}
</script>