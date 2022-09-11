<template>

  <div class="container-fluid">

    <!-- Navbar -->
    <Navbar />
    <!-- End of Navbar -->

    <!-- Main -->
    <div class="home">
      <Main />
    </div>

    <!-- End of Main -->

  </div>

  <!-- Footer -->
  <Footer />
  <!-- End of Footer -->

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
  padding: 0;
}


@media screen and (max-width: 890px) {
  div.home {
    padding: 0rem 0 8.5rem 0;
  }
}

@media screen and (max-width: 400px) {
  div.home {
    padding: 3.5rem 0 5rem 0;
  }
}

@media screen and (max-width: 320px) {
  div.home {
    padding: 2.5rem 0 5.5rem 0;
  }
}
</style>