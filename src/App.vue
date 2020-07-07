<template>
  <div id="app" class="container">
    <h1>VueJs</h1>

    <Post>
      <h2 slot="cabecalho">Components no Vue</h2>

      <p class="h3">Components são uma peça do Vue</p>
      <span>...</span>

      <small slot="rodape">por Gerson Barros</small>

      <template slot="botao">
        Detalhes
      </template>
    </Post>

  </div>
</template>

<script>
import Post from './components/Post.vue'
export default {
  components: {
    Post
  }
}
</script>