<template>
  <form class="card card-w30" @submit.prevent="submitHandler">
    <div class="form-control">
      <label for="type">Тип блока</label>
      <select id="type" v-model="contentModel">
        <option value="title">Заголовок</option>
        <option value="subtitle">Подзаголовок</option>
        <option value="avatar">Аватар</option>
        <option value="text">Текст</option>
      </select>
    </div>

    <div class="form-control">
      <label for="value">Значение</label>
      <textarea id="value" rows="3" v-model="textarea"></textarea>
    </div>
    <Btn color="primary" :disabled="disabled">Добавить</Btn>
  </form>
</template>

<script>
import Btn from '@/components/Btn'

export default {
  // emits: ['submitHandler'],
  data() {
    return {
      contentModel: 'title',
      textarea: '',
    }
  },
  methods: {
    submitHandler() {
      console.log(this.contentModel, this.textarea)
      this.textarea = ''
    },
  },
  computed: {
    disabled() {
      return this.textarea.length < 4
    },
  },
  components: { Btn },
}
</script>

<style lang="scss" scoped></style>
