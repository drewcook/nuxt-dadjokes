<template>
  <form @submit.prevent="onSubmit">
    <input type="text" v-model="term" placeholder="Search for a joke..." />
    <input type="submit" value="Search" />
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

<style></style>
