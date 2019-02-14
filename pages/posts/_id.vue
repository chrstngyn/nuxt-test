<template>
  <div class="container">
    <article>
      <h1 class="title">{{post.title}}</h1>
      <p>{{post.content}}</p>
    </article>

    <aside>
      <h3>Posts you might enjoy</h3>
      <ul>
        <li v-for="related in relatedPosts">
          <nuxt-link :to="{name: 'posts-id', params: {id: related.id}}">
            {{related.title}}
          </nuxt-link>
        </li>
      </ul>
    </aside>

  </div>
</template>

<script>
  export default {
    data() {
      return {
        id: this.$route.params.id,

      }
    },

    computed: {
      post() {
        // access store:
        // this.$store -> navigate to state
        // posts -> posts module
        // all -> get all posts that live in all property
        return this.$store.state.posts.all.find(post => post.id === this.id)
      },

      relatedPosts() {
        return this.$store.state.posts.all.filter(post => post.id)
      }
    }
  }
</script>

<!-- scoped attribute: overwrite global styles found in head on sibling /descendant elements -->
<style scoped>
  .container {
    display: flex;
    justify-content: space-between;
    line-height: 1.5;
  }

  article * {
    margin-bottom: 1rem;
  }

  aside {
    min-width: 280px;
    min-height: 280px;
  }

  .title {
    font-size: 2rem;
  }

</style>
