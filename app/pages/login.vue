<template>
  <NuxtLayout name="auth">
    <div class="flex items-center justify-center h-full">
      <div class="w-full max-w-sm space-y-8">
        <p class="text-2xl font-bold">Login</p>
        <div class="grid grid-cols-2 gap-3">
          <div class="col-span-1">
            <UButton size="xl" variant="outline" color="white" block>
              <UIcon name="i-logos-google-icon" class="w-5 h-5" />
            </UButton>
          </div>

          <div class="col-span-1">
            <UButton size="xl" variant="outline" color="white" block>
              <UIcon name="i-logos-apple" class="w-5 h-5 filter invert-0 dark:invert" />
            </UButton>
          </div>
        </div>
        <UDivider label="Or login with email and password" />
        <UForm :schema="schema" :state="state" class="space-y-4" @submit="onSubmit">
          <UFormGroup label="Email" name="email">
            <UInput v-model="state.email" variant="outline" color="gray" size="xl" />
          </UFormGroup>

          <UFormGroup label="Password" name="password">
            <UInput v-model="state.password" size="xl" variant="outline" color="gray" type="password" />
          </UFormGroup>

          <UButton type="submit" size="xl" color="primary">
            Continue
          </UButton>
        </UForm>

        <UButton type="submit" size="xl" variant="outline">
          Don't have an account? Sign up
        </UButton>
      </div>
    </div>
  </NuxtLayout>
</template>

<script setup>
import { object, string } from 'yup'

const schema = object({
  email: string().email('Invalid email').required('Required'),
  password: string()
    .min(8, 'Must be at least 8 characters')
    .required('Required')
})

const state = reactive({
  email: undefined,
  password: undefined
})

async function onSubmit (event) {
  // Do something with event.data
  console.log(event.data)
}
</script>
