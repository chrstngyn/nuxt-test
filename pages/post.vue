<template>
    <div class="container">
      <article>
        <h1 class="title">Vietnamese iced coffee</h1>
        <p>Vietnamese iced coffee is made with  is made using medium to coarse ground dark roast Vietnamese-grown coffee with a small metal Vietnamese drip filter.</p>
      </article>
    </div>
</template>

<script>
    export default {
        name: "post"
    }
</script>

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
