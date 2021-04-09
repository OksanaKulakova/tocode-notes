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
      notes: [
        {
          title: 'Learn vue 3',
          tags: ['work']
        },
        {
          title: 'Finish course',
          tags: ['home', 'work']
        },
        {
          title: 'Hello world',
          tags: []
        }
      ]
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
