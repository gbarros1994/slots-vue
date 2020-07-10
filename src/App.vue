<template>
  <div id="app" class="container">

    <h1>Components dinâmicos</h1>
    <PostsLista :posts="posts"/>

    <hr>

    <h1>Slot com scopo</h1>

    <button @click="componetSelecionado = 'Home'">Home</button>
    <button @click="componetSelecionado = 'PostsLista'">Posts</button>
    <button @click="componetSelecionado = 'Sobre'">Sobre</button>

    <button @click="componetSelecionado = 'Assincrono'">Assincrono</button>

    <p> {{ componetSelecionado }}</p>

  <!--MANTEM MEU
   COMPONENT VIVO, 
   INCLUDE DIZ O QUE QUERO MANTER EM CASH
   exclude nao mantem em cash
   max excluid o que foi acessado por ultimo-->
  <keep-alive include="Sobre" exclude="Home" max>
    <component
      :is="componetSelecionado"
      v-bind="propsAtuais">
    </component>
  </keep-alive>
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
    Assincrono: () => ({
      component: import('./components/Assincrono.vue'),
      loading: { template: '<p>Carregando...</p>'},
      error: { template: '<h1>erro</h1>'},
      delay: 200,
      timeout: 3000
    }),
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