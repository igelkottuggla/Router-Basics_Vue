<template>
    <div id="nav">
        <router-link to="/">Home</router-link> |
        <router-link :to="{ name: 'About' }">About</router-link> |
        <router-link :to="{ name: 'Jobs' }">Jobs</router-link>
    </div>
    <router-view />

    <div class="btns-container">
        <button @click="redirect" class="router-btn">Redirect to Home</button>
        <button @click="back" class="router-btn">Go Back</button>
        <button @click="forward" class="router-btn">Go Forward</button>
    </div>
</template>

<script>
export default {
    methods: {
        redirect() {
            this.$router.push({ name: 'Home' });
        },
        back() {
            this.$router.go(-1);
        },
        forward() {
            this.$router.go(+1);
        },
    },
};
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    max-width: 960px;
    margin: 0 auto;
}
#app p {
    text-align: left;
}
#nav {
    padding: 30px;
}
#nav a {
    font-weight: bold;
    color: #2c3e50;
    text-decoration: none;
    padding: 10px;
    border-radius: 4px;
}
#nav a:hover {
    background-color: firebrick;
    color: white;
}
#nav a.router-link-exact-active {
    color: white;
    background: crimson;
}
.btns-container {
    margin-top: 50px;
}
.router-btn {
    margin: 0 10px;
    padding: 10px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}
.router-btn:hover {
    background-color: crimson;
    color: white;
}
</style>
