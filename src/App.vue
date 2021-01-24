<template>
  <div class="container column">
    <Form @add-block="addBlock" />
    <Resume :blocks="blocks" />
  </div>
  <div class="container">
    <Loader v-if="loading" />
    <Comments v-else :comments="comments" @load-comments="loadComments" />
  </div>
</template>

<script>
import Form from '@/components/Form.vue'
import Resume from '@/components/Resume.vue'
import Loader from '@/components/Loader.vue'
import Comments from '@/components/Comments.vue'
import axios from 'axios'

export default {
  data() {
    return {
      blocks: [],
      comments: [],
      loading: false,
    }
  },
  methods: {
    addBlock(block) {
      this.blocks.push(block)
    },
    async loadComments() {
      this.loading = true

      const { data } = await axios.get(
        'https://jsonplaceholder.typicode.com/comments?_limit=5'
      )

      this.comments = Object.keys(data).map((comment) => {
        return {
          ...data[comment],
        }
      })

      this.loading = false
    },
  },
  components: {
    Form,
    Resume,
    Loader,
    Comments,
  },
}
</script>

<style></style>
