<template>
  <div>
    <nuxt-link to="/jokes">Back To Jokes</nuxt-link>
			<h3>
				{{joke.setup
					? (joke.setup.includes('.') || joke.setup.includes('!'))
						? joke.setup
						: `${joke.setup}?`
					: ''
				}}
			</h3>
			<p>
				<em>
					{{joke.punchline
						? (joke.setup.includes('.') || joke.setup.includes('!'))
							? ''
							: joke.punchline
						: ''
					}}
				</em>
			</p>
		</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      joke: {},
    }
  },
  async created() {
    try {
      // Get joke info
      const res = await this.$axios.$get(
        `https://dad-jokes.p.rapidapi.com/joke/${this.$route.params.id}`
      )
      this.joke = res.body
    } catch (ex) {
      console.log(ex)
    }
  },
  head() {
    return {
      title: `DadJokes | ${this.joke.setup}`,
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
h3 {
  margin-top: 2rem;
  text-align: center;
}
p {
  margin: 1rem auto;
  text-align: center;
}
</style>
