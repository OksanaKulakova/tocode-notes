<template>
  <div class="md-body">
    <From @onSubmit="handleSubmit" />
  </div>
</template>

<script>
import From from '@/components/Notes/Form.vue'
export default {
  components: { From },
  methods: {
    handleSubmit(title) {
      console.log(title)
    }
  }
}
</script>
