<template>
    <div class="container">
        <h4>Morning Brew Dad Jokes!</h4>
        <search-dad-jokes />
    </div>
</template>

<script>
import SearchDadJokes from './SearchDadJokes.vue'
export default {
    name: 'DadJokes',
    components: {
        SearchDadJokes
    }
}
</script>

<style>
    .container {
        width: 35%;
        border-radius: 20px;
        padding: 50px 10px 50px 10px;
        background-color: white;
        margin-top: 120px;
    }
    h4 {
        margin-bottom: 5%;
    }
</style>