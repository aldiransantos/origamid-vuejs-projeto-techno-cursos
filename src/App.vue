<template>
    <div id="app">
        <HeaderComponent />
        <router-view class="container"></router-view>
    </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue';

export default {
    components: {
        HeaderComponent,
    },
};
</script>

<style lang="scss">
body {
    margin: 0;
    font-family: 'Avenir', Arial, Helvetica, sans-serif;
    color: #234;
}
ul {
    list-style: none;
    padding: 0;
    margin: 0;
}
a {
    font-weight: bold;
    text-decoration: none;
    color: #234;
}
a.router-link-active {
    color: #4b8;
}

img {
    max-width: 100%;
}

.container {
    max-width: 800px;
    margin: 0 auto;
    padding: 20px;
}
.v-enter {
    opacity: 0;
    transform: translate3d(-20px, 0, 0);
}
.v-enter-active {
    transition: all 0.3s;
}
.conteudo {
    display: grid;
    grid-template-columns: 1fr minmax(200px, 400px);
    grid-gap: 30px;
}

@media screen and (max-width: 600px) {
    .conteudo {
        display: block;
    }
}
</style>
