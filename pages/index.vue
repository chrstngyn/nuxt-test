<template>
  <v-layout
    column
    justify-center
    align-center
  >
    <v-flex
      xs12
      sm8
      md6
    >
      <div class="text-xs-center">
        <logo />
      </div>
      <div class="links">
        <nuxt-link
          v-for="post in posts"
          :to="{name: 'posts-id', params:{id: post.id}}"
          :key="post.id"
          class="button--grey"
        >
          {{post.title }}
        </nuxt-link>
      </div>
    </v-flex>
  </v-layout>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  },

  // computed property that grabs posts from store
  computed: {
    posts () {
      return this.$store.state.posts.all
    }
  }
}
</script>
