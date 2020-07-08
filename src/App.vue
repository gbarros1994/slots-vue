<template>
  <div id="app" class="container">

    <h1>Components dinâmicos</h1>
    <PostsLista :posts="posts"/>

    <hr>

    <h1>Slot com scopo</h1>

    <button @click="componetSelecionado = 'Home'">Home</button>
    <button @click="componetSelecionado = 'PostsLista'">Posts</button>
    <button @click="componetSelecionado = 'Sobre'">Sobre</button>

    <p> {{ componetSelecionado }}</p>

    <component :is="componetSelecionado"
    v-bind="propsAtuais"></component>

    <Home/>
    <Sobre/>
    <!-- <PostsLista :posts="posts">
      <template slot-scope="{ meuPost }">
        <h2>{{ meuPost.titulo }}</h2>
        <p>{{ meuPost.conteudo }}</p>
        <small>{{ meuPost.autor }}</small>
      </template>
    </PostsLista> -->

  </div>
</template>

<script>
import Home from './components/Home.vue'
import PostsLista from './components/PostsLista.vue'
import Sobre from './components/Sobre.vue'

export default {
  components: {
    Home,
    PostsLista,
    Sobre
  },
  data() {
    return {
      componetSelecionado: 'Home',
      posts: [
        { id: 1, titulo: 'Components no Vue', conteudo: 'Componetens são legais', autor: 'Gerson'},
        { id: 2, titulo: 'Components no Vue', conteudo: 'Componetens são legais', autor: 'Carlos'}
      ]
    }
  },
  computed: {
    propsAtuais() {
      return this.componetSelecionado === 'PostsLista' ? { posts : this.posts } : {}
    }
  },
}
</script>