<template>
  <form class="card card-w30" @submit.prevent="submit">
    <div class="form-control">
      <label for="type">Тип блока</label>
      <select id="type" v-model="typeBlock">
        <option value="title">Заголовок</option>
        <option value="subtitle">Подзаголовок</option>
        <option value="avatar">Аватар</option>
        <option value="text">Текст</option>
      </select>
    </div>

    <div class="form-control">
      <label for="value">Значение</label>
      <textarea id="value" rows="3" v-model="value"></textarea>
    </div>
    <Btn color="primary" :disabled="disabled">Добавить</Btn>
  </form>
</template>

<script>
import Btn from '@/components/Btn'

export default {
  emits: ['add-block'],
  data() {
    return {
      typeBlock: 'title',
      value: '',
    }
  },
  methods: {
    submit() {
      this.$emit('add-block', {
        typeBlock: this.typeBlock,
        value: this.value,
        id: Date.now(),
      })
      this.typeBlock = 'title'
      this.value = ''
    },
  },
  computed: {
    disabled() {
      return this.value.length < 4
    },
  },
  components: { Btn },
}
</script>
