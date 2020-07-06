<template>
    <div class="post">
        <div class="post-cabecalho">
            <slot name="cabecalho"></slot>
        </div>
        <div class="post-conteudo">
            <slot name="conteudo"></slot>
        </div>
        <div class="post-rodape">
            <slot name="rodape"></slot>
        </div>
    </div>
</template>

<style lang="css" scoped>
    .post {
        margin: 15px auto;
    }

    .post-cabecalho {
        padding: 5px 15px;
    }

    .post-conteuto {
        font-size: 16px;
    }

    .post-rodape {
        font-style: italic;
    }
</style>