<template>
  <p v-if="true">
    <button class="btn primary">Загрузить комментарии</button>
  </p>
  <div v-else class="card">
    <h2>Комментарии</h2>
    <ul class="list">
      <li class="list-item">
        <div>
          <p><strong>test@microsoft.com</strong></p>
          <small
            >Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eligendi,
            reiciendis.</small
          >
        </div>
      </li>
    </ul>
  </div>
  <!-- <Loader /> -->
</template>

<script>
// import Loader from '@/components/Loader'
export default {
  components: {
    // Loader,
  },
}
</script>

<style lang Loader="scss" scoped></style>
