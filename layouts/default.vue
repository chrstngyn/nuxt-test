<template>
  <v-app dark>
    <div class="container">
      <NavBar />
      <nuxt />
    </div>

    <v-footer
      :fixed="fixed"
      app
    >
      <span>&copy; 2019</span>
    </v-footer>
  </v-app>
</template>

<script>
  import NavBar from '@/components/NavBar'

  export default {
    components: {
      NavBar
    }
  }
</script>

