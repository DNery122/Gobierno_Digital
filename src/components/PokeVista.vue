<template>
    <div id="card">
        <img v-bind:src="img" class="card-img-top" alt="...">
        <div class="card-body">
            <h2 class="card-title">{{nombre}}</h2>
            <a href="#" class="btn btn-primary">Ver datalles</a>
        </div>
    </div>
</template>

<script>
import axios from 'axios';

export default {
    data() {
        return {
            nombre: null,
            img: null
        };
    },
    mounted() {
        this.getTodos();
    },
    methods: {
        getTodos() {
            axios.get(this.url).then(response => {
                console.log(response.data);
                this.nombre = response.data.name;
                this.img = response.data.sprites.front_default;
            }).catch(e => console.log(e));
        }
    },
    name: 'PokeVista',
    props: {
        url: String
    }
}
</script>

<style>
#card {
    /* background-image: url("../assets/fondo.jpg"); */

    background-color: #f0932b;
    border-radius: 5%;
}
</style>