<template>
  <div>
		<h1>Welcome to DadJokes!</h1>
    <p>
			Welcome to the best corny dad jokes app on the web.  You can check out different jokes by category, or search for jokes directly.
		</p>
		<p>
			Check out the jokes page!
		</p>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: 'DadJokes | Welcome to DadJokes',
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
