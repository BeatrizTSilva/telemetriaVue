<template>
    <div>
        <h1>Hello from Home component</h1>
        <h1>{{data}}</h1>
        <h1>{{message}}</h1>
        <button v-on:click="hello" >Call Hello Function</button>
    </div>
</template>

<script>

export default {
    name:'Home',

    props: {
        data: String,
        message: String
    },
    methods: {
        hello(item) {
            alert("hello function called")
            console.log(item)
        }

    }
}
</script>
