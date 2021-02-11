<template>
  <div
    class="min-h-screen flex items-center justify-center bg-gray-50 dark:bg-gray-800 py-12 px-4 sm:px-6 lg:px-8"
  >
    <div class="max-w-md w-full space-y-8 text-indigo-600 dark:text-indigo-500">
      <div>
        <svg
          class="mx-auto h-12 w-auto purple-100"
          fill="none"
          stroke="currentColor"
          viewBox="0 0 24 24"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M12 11c0 3.517-1.009 6.799-2.753 9.571m-3.44-2.04l.054-.09A13.916 13.916 0 008 11a4 4 0 118 0c0 1.017-.07 2.019-.203 3m-2.118 6.844A21.88 21.88 0 0015.171 17m3.839 1.132c.645-2.266.99-4.659.99-7.132A8 8 0 008 4.07M3 15.364c.64-1.319 1-2.8 1-4.364 0-1.457.39-2.823 1.07-4"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
          />
        </svg>
        <h2
          class="mt-6 text-center text-3xl font-extrabold text-gray-900 dark:text-gray-300"
        >
          Sign in with your account
        </h2>
        <span> </span>
        <p class="mt-2 text-center text-sm text-gray-600 dark:text-gray-300">
          Or
          <NuxtLink
            :to="{ name: 'register' }"
            class="animate-pulse font-medium text-indigo-600 hover:text-indigo-500 dark:text-indigo-400"
          >
            register here.
          </NuxtLink>
        </p>
      </div>
      <div
        class="container bg-white dark:bg-gray-700 dark:border-gray-700 pl-8 pr-8 pb-8 pt-2 border border-gray-200 border-opacity-100 rounded"
      >
        <form action="#" class="space-y-6" method="POST">
          <div class="mt-4 rounded-md shadow-sm -space-y-px">
            <FormulateInput
              v-model="form.username"
              label="Email address"
              label-position="before"
              outer-class="mb-2"
              type="text"
              validation="required|email"
            ></FormulateInput>
            <FormulateInput
              v-model="form.password"
              label="Password"
              label-position="before"
              type="password"
              validation="required"
            ></FormulateInput>
          </div>
          <div class="flex items-center justify-between">
            <div class="flex items-center">
              <FormulateInput
                v-model="form.rememberMe"
                input-class="focus:ring-indigo-500 h-4 w-4 text-indigo-600 border-gray-300 rounded"
                label="Remember me"
                :label-class="['ml-6 -mt-6 block']"
                label-position="after"
                type="checkbox"
              />
            </div>
            <div class="text-sm">
              <a
                class="font-medium text-indigo-600 dark:text-indigo-400 hover:text-indigo-500 dark-hover:text-indigo-300"
                href="#"
              >
                Forgot your password?
              </a>
            </div>
          </div>
          <div>
            <Button
              :loading="false"
              class="mt-5 bg-indigo-600 hover:bg-indigo-700 focus:ring-indigo-500 text-white"
              type="submit"
              @click.native.prevent="login"
            >
              <template #text>Sign in</template>
            </Button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import Button from '@/components/Button'

export default {
  name: 'Index',
  components: { Button },
  data() {
    return {
      form: {
        username: '',
        password: '',
        rememberMe: false,
        autoLogin: false,
      },
      loading: false,
    }
  },
  methods: {},
}
</script>

<style></style>
