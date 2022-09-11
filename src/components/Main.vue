<template>
    <div class="main">

        <!-- Main Top BG -->
        <div class="main-top-bg"></div>
        <!-- End of Main Top BG -->

        <section class="main__content">
            <h1 class="main-text">URL SHortener</h1>
            <h4 class="main-subtitle">Shorten any URL link with a click</h4>
        </section>

        <section class="input__content">
            <!-- Input -->
            <Input />
            <!-- End of Input -->
        </section>

    </div>
</template>


<script>
import Input from '@/components/Input.vue';

export default {
    name: "Main",
    components: {
        Input,
    }
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

div.main {
    text-align: center;
    padding: 10rem 0rem 17.2rem 0rem;
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


@media screen and (max-width: 489px) {
    div.main-top-bg {
        width: 80px;
        height: 80px;
        left: 100px;
        top: 121px;
    }

    div.main {
        padding: 4rem 0rem 8rem 0rem;
    }

    h1.main-text {
        font-size: 46px;
        margin-top: 60px;
    }
}
</style>