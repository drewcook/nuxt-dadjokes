<template>
  <div>
    <h1>About Dad Jokes</h1>
    <p>
      This application is built using the <a href="https://nuxtjs.org" target="_blank">Nuxt.js framework</a>, which is a simple and intuitive framework for building applictions with Vue.js.
    </p>
		<p>
			This application also works with the third party API from <a href="https://dadjokes.io" target="_blank">DadJokes.io</a>.  It fetches and filters data for viewing and searching different jokes with unique categories.
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

<style scoped>
p {
	margin: 1rem 0;
	font-size: 18px;
}
</style>
