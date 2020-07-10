<template>
    <div>
        <h1>Sobre</h1>   

        <p v-if="autor">Autor: {{ autor }}</p>
        <input type="text" v-model="autor">
    </div>
</template>

<script>
export default {
    data() {
        return {
            autor: ''
        }
    },
    activated() {
        console.log('activated')
    },
    destroyed() {
        console.log('destroyed')
    },
    deactivated() {
        console.log('deactivated')
    }
}
</script>