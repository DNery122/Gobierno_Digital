<template>

    <header class="header">
        <label for="pokemonInput">Tipo de pokemon nombre o ID: </label>
        <input type="text" id="pokemonInput">
        <br>
        <div class="content">
            <div class="card" v-for="todo in todos" :key='todo.id'>
                <PokeVista :url = " todo.url "  />
            </div>
        </div>
    </header>
</template>

<script>

import axios from 'axios';
import PokeVista from './PokeVista.vue';

export default {
    data() {
        return {
            todos: null
        };
    },
    mounted() {
        this.getTodos();
    },
    methods: {
        getTodos() {
            axios.get("https://pokeapi.co/api/v2/pokemon?limit=8").then(response => {
                this.todos = response.data.results;
            }).catch(e => console.log(e));
        }
    },
    name: "PokeLista",
    components: { PokeVista }
}
</script>

<style>
.content {
    padding: 30px;
}

.card {
    width: 250px;
    display: inline-block;
    margin: 20px;
}
</style>