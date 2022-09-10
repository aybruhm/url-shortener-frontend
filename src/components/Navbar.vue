<template>
    <div class="nav-top-bg"></div>
    <nav class="navbar">
        <a class="navbar-brand" href="#">
            <img src="../assets/shortener-logo.png" alt="shortener-logo" class="img-responsive">
        </a>
    </nav>
    <div class="nav-bottom-bg"></div>
</template>


<script>

export default {
    name: "Navbar"
}
</script>


<style scoped>
div.nav-top-bg {
    position: absolute;
    width: 298px;
    height: 298px;
    left: -56px;
    top: -79px;
    border-radius: 50%;

    background: linear-gradient(196.73deg, #DEA4C4 55.16%, rgba(182, 193, 212, 0) 102.42%);
    opacity: 0.4;
}

div.nav-bottom-bg {
    position: absolute;
    width: 92px;
    height: 92px;
    left: 225px;
    top: 121px;
    border-radius: 50%;

    background: linear-gradient(196.73deg, #DEA4C4 55.16%, rgba(182, 193, 212, 0) 102.42%);
    opacity: 0.4;
}

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