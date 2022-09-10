<template>
    <div class="main-top-bg"></div>
    <section class="main__content">
        <h1 class="main-text">URL SHortener</h1>
        <h4 class="main-subtitle">Shorten any URL link with a click</h4>
    </section>
</template>


<script>
export default {
    name: "Main"
}
</script>


<style scoped>
div.main-top-bg {
    position: absolute;
    width: 148px;
    height: 148px;
    left: 400px;
    top: 234px;
    border-radius: 50%;

    background: linear-gradient(196.73deg, #DEA4C4 55.16%, rgba(182, 193, 212, 0) 102.42%);
    opacity: 0.4;
}

section.main__content {
    text-align: center;
    padding: 10rem 0rem 24.5rem 0rem;
}

h1.main-text {
    font-style: normal;
    font-weight: 900;
    font-size: 95px;
    margin-bottom: 0%;
    padding-bottom: 0%;
    letter-spacing: 0.065em;
    color: #000000;
}

h4.main-subtitle {
    font-style: normal;
    font-weight: 500;
    font-size: 24px;
    margin-top: 0%;
    padding-top: 0%;
    line-height: 40px;
    letter-spacing: 0.065em;
    color: #000000;
}
</style>