<template>
    <div>
        <div v-if="loading">
            <PageLoading />
        </div>
        <transition>
            <div v-if="data" class="conteudo">
                <div>
                    <h1>Sobre a {{ data.titulo }}</h1>
                    <p>{{ data.descricao }}</p>
                    <router-link class="btn-cursos" tag="button" to="/cursos"
                        >Cursos</router-link
                    >
                    <div>
                        <h2>Avaliações</h2>
                        <ul>
                            <li
                                v-for="avaliacao in data.avaliacoes"
                                :key="avaliacao.nome"
                            >
                                <h4>{{ avaliacao.nome }}</h4>
                                <p>{{ avaliacao.descricao }}</p>
                            </li>
                        </ul>
                    </div>
                </div>
                <img src="@/assets/aprender.png" alt="Aprenda Web Design" />
            </div>
        </transition>
    </div>
</template>

<script>
import fetchData from '../mixins/fetchData';

export default {
    name: 'home-view',
    mixins: [fetchData],
    created() {
        this.fetchData('/home');
    },
};
</script>

<style scoped>
.btn-cursos {
    border: none;
    background: #4b8;
    border-radius: 4px;
    color: white;
    cursor: pointer;
    margin-bottom: 10px;
    margin-bottom: 40px;
    padding: 15px 40px;
    font-size: 1rem;
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    box-shadow: 0 4px 2px rgba(0, 0, 0, 0.1);
}
</style>
