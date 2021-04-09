<template>
  <div class="md-body">
    <Form @onSubmit="handleSubmit" />
    <List @onRemove="handleRemove" :items="notes" />
  </div>
</template>

<script>
import Form from '@/components/Notes/Form.vue'
import List from '@/components/Notes/List.vue'
export default {
  components: { Form, List },
  data() {
    return {
      notes: ['task 1', 'task 2', 'task 3']
    }
  },
  methods: {
    handleSubmit(title) {
      console.log(title)
    },
    handleRemove(index) {
      this.notes.splice(index, 1)
    }
  }
}
</script>
