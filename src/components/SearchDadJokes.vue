<template>
    <label for="search-jokes">Search Jokes: </label>
    <input type="text" id="search-jokes" v-model='searchTerm'>
    <button v-on:click="search">Search!</button>
    <ul>
        <li v-if="!jokes">No Jokes Found</li>
        <li v-else v-for="joke in jokes" v-bind:key="joke.id" class="card">{{joke.joke}}</li>
    </ul>
</template>

<script>
import axios from 'axios'
export default {
    name: 'SearchDadJokes',
    data() {
        return {
            jokes: [],
            searchTerm: "",
        }
    },
    methods: {
        search() {
            const options = {
                headers: {'Accept': 'application/json'},
            };
            axios.get(`https://icanhazdadjoke.com/search?term=${this.searchTerm}`, options)
            .then(res => {
                if (res.data.results.length > 0) {
                    this.jokes = res.data.results;
                } else {
                    this.jokes = null;
                }
            })
        }
    }
}
</script>

<style>
    li {
        list-style: none;
        padding: 20px;
        margin-bottom: 7px;
    }
    .card {
        box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
        transition: 0.3s;
        border-radius: 10px;
    }
    .card:hover {
        box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
    }

    #search-jokes {
        margin-left: 4px;
        margin-right: 10px;
    }
    button {
        border-radius: 7px;
        padding: 4px 6px 4px 6px;
        background-color: black;
        color: white;
        font-size: 13px;
    }
    input {
        border-radius: 7px;
    }
  
</style>