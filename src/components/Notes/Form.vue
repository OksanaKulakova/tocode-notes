<template>
  <form class="note-form" @submit.prevent="onSubmit">
    <textarea required v-model="value" placeholder="Type ur note" />
    <TagsList @onTagClick="handleTagClick" :items="tags" />
    <button class="btn btnPrimary" type="submit">Add new note</button>
  </form>
</template>

<script>
import TagsList from '@/components/TagsList.vue'
export default {
  components: { TagsList },
  data() {
    return {
      value: '',
      tags: ['home', 'work', 'travel']
    }
  },
  methods: {
    handleTagClick(tag) {
      console.log(tag)
    },
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
  textarea {
    margin-bottom: 0;
  }
}
</style>
