<template>
  <div class="card card-w70">
    <!-- <component :is="componentName" v-if="blocks.length"></component> -->
    <component :is="componentName"></component>
    <!-- <resumeTitle />
    <resumeAvatar />
    <resumeSubtitle />
    <resumeText /> -->

    <h3>Добавьте первый блок, чтобы увидеть результат</h3>
  </div>
</template>

<script>
import resumeTitle from '@/components/resumeTitle'
import resumeAvatar from '@/components/resumeAvatar'
import resumeSubtitle from '@/components/resumeSubtitle.vue'
import resumeText from '@/components/resumeText.vue'

export default {
  data() {
    return {
      blocks: [],
    }
  },
  computed: {
    componentName() {
      if (this.contentModel === 'title') {
        return 'resumeTitle'
      }
      return 'resumeAvatar'
    },
  },
  components: {
    resumeTitle,
    resumeAvatar,
    resumeSubtitle,
    resumeText,
  },
}
</script>

<style lang="scss" scoped></style>
