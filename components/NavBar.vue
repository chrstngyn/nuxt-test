<template>
    <nav class="nav">
      <div class="logo">
        <nuxt-link :to="{name: 'index'}" class="logo text-lg">
          Navigation Bar
        </nuxt-link>

        <span class="subheader">A Vue School Course</span>
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
