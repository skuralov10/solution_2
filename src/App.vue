<template>
  <div class="container column">
    <Form />
    <Resume />
  </div>
  <!-- <div class="container">
    <Comments />
  </div> -->
</template>

<script>
import Form from '@/components/Form.vue'
import Resume from '@/components/Resume.vue'
// import Comments from '@/components/Comments.vue'
export default {
  components: {
    Form,
    Resume,
    // Comments,
  },
}
</script>

<style>
.avatar {
  display: flex;
  justify-content: center;
}

.avatar img {
  width: 150px;
  height: auto;
  border-radius: 50%;
}
</style>
