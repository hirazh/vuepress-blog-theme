<template>
    <div class="nav-wrapper">
        <nav class="nav-bar">
            <h4>Hiraz's Blog</h4>
            <h4>
                <router-link class="nav-router-link" to="/">Home</router-link>
            </h4>
        </nav>
    </div>
</template>

<script>
export default {
    
}
</script>

<style scoped>
nav {
    display: flex;
    align-items: center;
    font-family: 'Open Sans', sans-serif;
}
.nav-bar h4 {
    margin-left: 3%;
}

.nav-router-link {
    color: #f0f0f0;
    text-decoration-line: none;
}
</style>

