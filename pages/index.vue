<template>
  <v-app>
    <!-- Component navbar of page -->
    <Navigation />
    <v-main>
      <!-- Component Carousel of page -->
      <Carousel />
      <!-- Component US of page -->
      <Us />
      <!-- Component Portfoliio of page -->
      <Portfolio />
      <!-- Component Contact US of page -->
      <Contact />
    </v-main>
    <v-footer>
      <!-- Component Footer of page -->
      <Footer />
    </v-footer>
  </v-app>
</template>

<script>
import Navigation from '../components/navigation'
import Carousel from '../components/carousel'
import Us from '../components/us'
import Portfolio from '../components/portfolio'
import Contact from '../components/contact'
import Footer from '../components/footer'
export default {
  components: {
    Navigation,
    Carousel,
    Us,
    Portfolio,
    Contact,
    Footer,
  },
}
</script>
