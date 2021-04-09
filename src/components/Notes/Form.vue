<template>
  <form class="note-form" @submit.prevent="onSubmit">
    <textarea required v-model="value" placeholder="Type ur note" />
    <button class="btn btnPrimary" type="submit">Add new note</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      value: ''
    }
  },
  methods: {
    onSubmit() {
      this.$emit('onSubmit', this.value)
      this.value = ''
    }
  }
}
</script>

<style lang="scss">
.note-form {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
</style>
