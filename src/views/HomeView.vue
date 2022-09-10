<template>
  <div class="home">

    <div class="container-fluid">

      <!-- Navbar -->
      <Navbar />
      <!-- End of Navbar -->

      <!-- Main -->
      <Main />
      <!-- End of Main -->

    </div>

    <!-- Footer -->
    <Footer />
    <!-- End of Footer -->

  </div>
</template>


<script>
// @ is an alias to /src
import Navbar from '@/components/Navbar.vue';
import Main from '@/components/Main.vue';
import Footer from '@/components/Footer.vue';

export default {
  name: 'HomeView',
  components: {
    Navbar,
    Main,
    Footer,
  }
}
</script>


<style scoped>
div.home {
  background: linear-gradient(138.95deg, #FFA36A 23.27%, #EFC5C4 97.22%);
  height: 100vh;
}
</style>