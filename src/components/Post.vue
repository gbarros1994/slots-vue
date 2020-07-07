<template>
    <div class="col-lg-12">
        <div class="post-cabecalho">
            <slot name="cabecalho"></slot>
        </div>
        <div class="post-conteudo">
            <slot></slot>
        </div>
        <div class="post-rodape">
            <slot name="rodape"></slot>
            <a href="" class="btn btn-success d-block">
                <slot name="botao">Ler mais...</slot>
            </a>
        </div>
    </div>
</template>

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