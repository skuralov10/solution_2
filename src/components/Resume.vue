<template>
  <div class="card card-w70">
    <template v-if="blocks.length">
      <component
        v-for="block in blocks"
        :key="block.id"
        :is="'Resume-' + block.typeBlock"
        v-bind="{ value: block.value }"
      ></component>
    </template>

    <h3 v-else>Добавьте первый блок, чтобы увидеть результат</h3>
  </div>
</template>

<script>
import ResumeTitle from '@/components/ResumeTitle'
import ResumeAvatar from '@/components/ResumeAvatar'
import ResumeSubtitle from '@/components/ResumeSubtitle.vue'
import ResumeText from '@/components/ResumeText.vue'

export default {
  props: ['blocks'],
  components: {
    ResumeTitle,
    ResumeAvatar,
    ResumeSubtitle,
    ResumeText,
  },
}
</script>
