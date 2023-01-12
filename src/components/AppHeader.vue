<script >
    export default {
        name: 'AppHeader',
    }
</script>

<template>
    <div class="container">
        <div class="logo">
            <img src="../assets/imgs/main-logo.jpg" alt="">
            <h1>Yu-Gi-Oh</h1>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    .container {
        width: 75%;
        margin: auto;
    }

    .logo {
        display: flex;
        align-items: center ;  
        padding: 2rem;

        img {
            width: 10%;
            margin-right: 1rem;
        }
    }
</style>