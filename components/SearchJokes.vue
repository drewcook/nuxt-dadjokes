<template>
  <form @submit.prevent="onSubmit">
		<div class="group">
			<input type="text" v-model="term" placeholder="Search for a joke..." />
			<input type="submit" value="Let's Go!" />
		</div>
  </form>
</template>

<script>
export default {
  name: 'SearchJokes',
  data() {
    return {
      term: '',
    }
  },
  methods: {
    onSubmit() {
      this.$emit('search-joke', this.term)
      this.term = ''
    },
  },
}
</script>

<style scoped>
.group {
	display: flex;
}
input {
	/* width: 100%; */
	padding: 13px 20px;
	border: 1px solid #ccc;
	border-radius: 4px;
	font-size: 18px;
	flex-grow: 5;
}
input[type="submit"] {
	flex-grow: 1;
	font-size: 16px;
	background: #526488;
	color: #fff;
}
</style>
