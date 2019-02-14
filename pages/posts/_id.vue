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
            <a :href="`/posts/${related.id}`">{{related.title}}</a>
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

          posts: [
            {
              id: 'history',
              title: 'History of Vietnamese Coffee',
              content: 'Coffee in Vietnam began in the 18th century when both French and Dutch colonial settlers brought the coffee phenomenon (and coffee plants themselves) along with them, starting large plantations in the process. The French also brought another element that was critical to the development of Vietnamese coffee: Sweetened condensed milk.',
            },

            {
              id: 'ingredients',
              title: 'Unique Ingredients of Vietnamese Coffee',
              content: 'The Phin, Robusta Beans, Sweetened Condensed Milk',
            },

          ]
        }
      },

      computed: {
        post () {
          return this.posts.find(post => post.id === this.id)
        },

        relatedPosts () {
          return this.posts.filter(post => post.id)
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
