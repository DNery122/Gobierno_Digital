<template>
   
   <header class = "header">
<label for="pokemonInput">Tipo de pokemon nombre o ID: </label>
    <input type="text" id="pokemonInput">


<ol>
    <li v-for="todo in todos" :key = 'todo.id'>
    {{todo.name}}
    </li>
</ol>

   </header>
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