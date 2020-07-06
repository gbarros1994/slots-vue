<template>
  <div id="app" class="container">
    <h1>Vue js</h1>
    <Post>
      <h1 slot="cabecalho">kakskas</h1>
      <p slot="conteudo">Testando slots</p>
      <small slot="rodape">Por Gerson Barros</small>
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

<style lang="css" scoped>
  .container {
    width: 960px;
    margin: auto;
  }
</style>