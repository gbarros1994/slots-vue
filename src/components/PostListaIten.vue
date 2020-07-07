<template>
    <div class="col-lg-12">

        <slot>
            <div class="post-cabecalho">
                <h2>{{ post.titulo }}</h2>
            </div>
            <div class="post-conteudo">
                <h5>{{ post.conteudo }}</h5>
            </div>
            <div class="post-rodape">
                <small>{{ post.autor }}</small>
                <a href="" class="btn btn-success d-block mb-3">Ler mais...
                </a>
            </div>
        </slot>


    </div>
</template>

<script>
export default {
    props: {
        post: {
            type: Object,
            required: true
        }
    }
}
</script>

<style lang="css" scoped>
    .post-cabecalho {
        padding: 5px 12px;
        background-color: #eee;
    }

    .post-conteudo {
        font-size: 16px;
    }

    .post-rodape {
        font-style: italic;
    }
</style>