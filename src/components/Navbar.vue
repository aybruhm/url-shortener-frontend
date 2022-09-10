<template>
    <nav class="navbar">
        <a class="navbar-brand" href="#">
            <img src="../assets/shortener-logo.png" alt="shortener-logo" class="img-responsive">
        </a>
    </nav>
</template>


<script>

export default {
    name: "Navbar"
}
</script>


<style scoped>
nav.navbar {
    padding: 30px;
    box-shadow: 0px 0px 0px 0px;
}

a.navbar-brand>img {
    width: 250px;
}

@media screen and (max-width: 489px) {
    a.navbar-brand>img {
        width: 200px;
    }
}
</style>