<template>
    <nav class="nav">
      <div class="logo">
        <nuxt-link :to="{name: 'index'}" class="logo text-lg">
          Home
        </nuxt-link>

        <span class="subheader">Subheader </span>
      </div>
    </nav>
</template>

<script>
    export default {
        name: "NavBar"
    }
</script>

<style scoped>

</style>
