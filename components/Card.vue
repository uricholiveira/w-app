<template>
  <div
    class="my-1 px-1 w-full md:w-1/2 lg:my-4 lg:px-4 lg:w-1/3 border-2 border-gray-500 border-opacity-25 overflow-hidden rounded-lg shadow-lg dark:bg-gray-900 dark:text-gray-300 h-64"
    @click="$emit('click', $event.target.value)"
  >
    <div class="text-center text-2xl font-extrabold p-2 uppercase">
      {{ title }}
    </div>
    <div class="flex justify-between p-4">
      <div>Itens 1/3</div>
      <div>
        <div class="flex -space-x-1 overflow-hidden">
          <img
            class="inline-block h-6 w-6 rounded-full ring-2 ring-white"
            src="https://images.unsplash.com/photo-1491528323818-fdd1faba62cc?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80"
            alt=""
          />
          <img
            class="inline-block h-6 w-6 rounded-full ring-2 ring-white"
            src="https://images.unsplash.com/photo-1550525811-e5869dd03032?ixlib=rb-1.2.1&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80"
            alt=""
          />
          <img
            class="inline-block h-6 w-6 rounded-full ring-2 ring-white"
            src="https://images.unsplash.com/photo-1500648767791-00dcc994a43e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2.25&w=256&h=256&q=80"
            alt=""
          />
          <img
            class="inline-block h-6 w-6 rounded-full ring-2 ring-white"
            src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80"
            alt=""
          />
        </div>
      </div>
    </div>
    <div class="flex flex-wrap justify-center text-center py-2">
      <div class="w-full">Valor total</div>
      <div class="w-full font-semibold text-gray-900 dark:text-gray-200">
        R$ {{ total }}
      </div>
    </div>
    <div class="flex flex-wrap justify-center text-center py-2">
      <div class="w-full">Valor restante</div>
      <div class="w-full font-semibold text-gray-900 dark:text-gray-200">
        R$ {{ remaining }}
      </div>
    </div>
    <div class="flex justify-center">
      <div
        class="h-2 relative max-w-xl rounded-full overflow-hidden pb-2 w-5/6"
      >
        <div class="w-full h-full bg-gray-200 absolute" />
        <div
          ref="bar"
          class="transition-all ease-out duration-1000 h-full bg-green-500 absolute w-full"
          :style="{ width: progress }"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    total: {
      type: Number,
      default: 0,
    },
    remaining: {
      type: Number,
      default: 0,
    },
    title: {
      type: String,
      default: 'Title card',
    },
    percent: {
      type: Number,
      default: 0,
    },
  },
  computed: {
    progress() {
      return this.percent + '%'
    },
  },
  created() {},
}
</script>

<style scoped></style>
