<template>
  <div class="min-h-screen">
    <div class="w-full px-12">
      <div
        class="py-20 font-semibold text-2xl flex justify-center dark:text-indigo-200"
      >
        <div>
          <h1>Hello {USER_NAME}, welcome back.</h1>
        </div>
      </div>
      <div class="flex justify-center gap-2">
        <FormulateInput
          v-model="searchText"
          placeholder="Pesquisa"
          type="text"
        />
      </div>
      <div class="container my-12 mx-auto px-4 md:px-12">
        <div class="flex flex-wrap -mx-1 lg:-mx-4">
          <!-- Column -->
          <Card
            title="MÓVEIS PRA NOSSA CASA"
            :total="8524.0"
            :remaining="7281.0"
            :percent="88"
            @click="
              $router.push({ name: 'home-detail-id', params: { id: '1' } })
            "
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Card from '~/components/Card'
export default {
  name: 'Home',
  components: { Card },
  data() {
    return {
      searchText: '',
    }
  },
  methods: {
    alert(value) {
      alert(value)
    },
  },
}
</script>

<style scoped></style>
