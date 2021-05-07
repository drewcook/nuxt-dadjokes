<template>
  <div>
    <h1>About Dad Jokes</h1>
    <p>
      This is an app that displays corny dad jokes. It is built with the Nuxt.js
      framework for building apps with Vue.js.
    </p>
  </div>
</template>

<script>
export default {
  // Improve SEO with custom head tags
  head() {
    return {
      title: 'DadJokes | About the App',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Best place for corny dad jokes',
        },
      ],
    }
  },
}
</script>

<style></style>
