<template>
    <div>
        <h1>HOLA MUNDO</h1>
    </div>
</template>

<script>

import axios from 'axios';

export default {
    data() {
        return {
            todos: null
        }
    },
    mounted() {
        this.getTodos();
    },
    methods: {
        getTodos() {
            axios.get('https://pokeapi.co/api/v2/pokemon/').then(response => {
                console.log(response.data.results);
                this.todos = response.data.results;
            }).catch(e => console.log(e));
        }
    },
    name: 'PokeLista',
}
</script>