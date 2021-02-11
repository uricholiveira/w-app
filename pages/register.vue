<template>
  <div
    class="min-h-screen flex items-center justify-center bg-gray-50 dark:bg-gray-800 py-12 px-4 sm:px-6 lg:px-8"
  >
    <div class="max-w-md w-full space-y-8 text-indigo-600 dark:text-indigo-500">
      <div>
        <svg
          class="mx-auto h-12 w-auto"
          fill="currentColor"
          stroke="currentColor"
          viewBox="0 0 20 20"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            clip-rule="evenodd"
            d="M11.3 1.046A1 1 0 0112 2v5h4a1 1 0 01.82 1.573l-7 10A1 1 0 018 18v-5H4a1 1 0 01-.82-1.573l7-10a1 1 0 011.12-.38z"
            fill-rule="evenodd"
          />
        </svg>
        <h2
          class="mt-6 text-center text-3xl font-extrabold text-gray-900 dark:text-gray-300"
        >
          Create your account
        </h2>
        <p class="mt-2 text-center text-sm text-gray-600 dark:text-gray-300">
          Or
          <NuxtLink
            :to="{ name: 'index' }"
            class="animate-pulse font-medium text-indigo-600 hover:text-indigo-500 dark:text-indigo-400"
          >
            sign in here.
          </NuxtLink>
        </p>
      </div>
      <div
        class="container bg-white dark:bg-gray-700 dark:border-gray-700 pl-8 pr-8 pb-8 pt-2 border border-gray-200 border-opacity-100 rounded"
      >
        <form action="#" class="space-y-6" method="POST">
          <div class="mt-4 rounded-md shadow-sm -space-y-px">
            <FormulateInput
              v-model="userForm.name"
              label="Name"
              label-position="before"
              type="text"
              validation="required"
            ></FormulateInput>
            <FormulateInput
              v-model="userForm.email"
              label="Email address"
              label-position="before"
              :outer-class="['pt-2']"
              type="text"
              validation="required|email"
            ></FormulateInput>
            <FormulateInput
              v-model="userForm.password"
              label="Password"
              label-position="before"
              :outer-class="['pt-2']"
              type="password"
              validation="required"
            ></FormulateInput>
          </div>

          <div>
            <Button
              :loading="false"
              class="mt-5 bg-indigo-600 hover:bg-indigo-700 focus:ring-indigo-500 text-white"
              type="submit"
              @click.native.prevent="register"
            >
              <template #text>Register</template>
            </Button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import Button from '~/components/Button'
export default {
  name: 'Register',
  components: { Button },
  data() {
    return {
      userForm: {
        name: '',
        email: '',
        password: '',
      },
    }
  },
  methods: {
    register() {
      this.$axios
        .post('user/', this.userForm)
        .then((response) => {
          console.log(response)
        })
        .catch((error) => {
          console.log(error.response)
        })
    },
  },
}
</script>

<style scoped></style>
