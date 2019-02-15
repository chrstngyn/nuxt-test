<template>
  <v-layout
    justify-center
    align-center
  >
    <v-flex
      xs12
      sm8
      md6
    >
      <div class="text-xs-center">
        <logo/>
      </div>
      <div class="coffeetime">
        <v-timeline light>
          <v-timeline-item
            v-for="(post, i) in posts"
            :key="i"
            fill-dot
          >
            <v-card>
              <v-card-title>{{post.timelinetitle}}</v-card-title>
              <v-card-text>
                <p>{{post.timelinecontent}}</p>
                <v-btn
                  :to="{name: 'posts-id', params:{id: post.id}}"
                  :key="post.id"
                  outline
                >
                  Learn more
                </v-btn>
              </v-card-text>
            </v-card>
          </v-timeline-item>
        </v-timeline>
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

    // data: () => ({
    //   items: [
    //     {
    //       color: 'red lighten-2',
    //       icon: 'mdi-star'
    //     },
    //
    //     {
    //       color: 'purple darken-1',
    //       icon: 'mdi-book-variant'
    //     },
    //
    //     {
    //       color: 'green lighten-1',
    //       icon: 'mdi-airballoon'
    //     },
    //
    //     {
    //       color: 'indigo',
    //       icon: 'mdi-buffer'
    //     },
    //
    //     {
    //       color: 'indigo',
    //       icon: 'mdi-buffer'
    //     }
    //   ]
    // }),

    // head method sets title to home page
    head() {
      return {
        title: 'Home Page'
      }
    },

    // computed property that grabs posts from store
    computed: {
      posts() {
        return this.$store.state.posts.all
      }
    }
  }
</script>
