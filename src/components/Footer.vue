<template>
    <footer class="shortener_footer">
        <p class="footer-text">
            Designed by the
            <a href="https://www.behance.net/martinmadami" target="_blank">UX Guy</a>
        </p>
    </footer>
</template>


<script>
export default {
    name: "Footer",
}
</script>


<style scoped>
footer {
    background: #000000;
    padding: 25px;
}

p.footer-text {
    text-align: center;
    font-weight: 400;
    font-size: 24px;
    line-height: 38px;
    letter-spacing: 0.065em;
    color: #FFA36A;
    margin-bottom: 0px;
}

a {
    color: #FFA36A;
}

@media screen and (max-width: 489px) {
    p.footer-text {
        font-size: 18px;
    }
}
</style>