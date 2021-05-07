<template>
  <div>
    <h2>Jokes</h2>
		<SearchJokes v-on:search-joke="searchJoke"/>
    <Joke v-for="joke in jokes" :key="joke._id" :joke="joke" />
  </div>
</template>

<script>
import Joke from '../../components/Joke'
import SearchJokes from '../../components/SearchJokes'
export default {
  components: {
    Joke,
		SearchJokes,
  },
  data() {
    return {
      jokes: [],
    }
  },
  async created() {
    try {
      // Get 50 Dad Jokes
      const res = await this.$axios.$get(
        'https://dad-jokes.p.rapidapi.com/joke/type/Dad%20Jokes?limit=50'
      )
      this.jokes = res.body
    } catch (ex) {
      console.log(ex)
    }
  },
	methods: {
		async searchJoke(term) {
			try {
				const res = await this.$axios.get(`https://dad-jokes.p.rapidapi.com/joke/search?term=${term}&limit=50`);
				this.jokes = res.data.body;
			} catch (ex) {
				console.log(ex)
			}
		}
	},
  head() {
    return {
      title: 'DadJokes | Jokes List',
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
