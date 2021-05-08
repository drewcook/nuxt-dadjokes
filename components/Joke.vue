<template>
  <nuxt-link :to="`jokes/${joke._id}`">
    <div class="joke">
      <h4>
				{{joke.setup
					? (joke.setup.includes('.') || joke.setup.includes('!'))
						? joke.setup
						: `${joke.setup}?`
					: ''
				}}
			</h4>
    </div>
  </nuxt-link>
</template>

<script>
export default {
  name: 'Joke',
  props: ['joke'],
}
</script>

<style scoped>
.joke {
  padding: 1rem;
  border: 1px dotted #ccc;
  margin: 1rem 0;
}
</style>
