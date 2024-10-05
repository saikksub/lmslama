<template>
  <NuxtLayout name="auth">
    <p class="text-2xl font-bold">Login</p>
    <div class="grid grid-cols-2 gap-3">
      <div class="col-span-2">
        <UButton size="xl" color="white" block>
          <UIcon name="i-logos-google-icon" class="w-5 h-5" />
          Sign in with Google
        </UButton>
      </div>
    </div>
    <div class="h-3" />
    <UDivider label="Or login with email and password" class="py-3" />
    <UForm :schema="schema" :state="state" class="space-y-4" @submit="onSubmit">
      <UFormGroup label="Email" name="email">
        <UInput v-model="state.email" variant="outline" size="xl" placeholder="Enter your email" />
      </UFormGroup>

      <UFormGroup label="Password" name="password">
        <UInput v-model="state.password" size="xl" variant="outline" type="password" placeholder="Enter your password" />
      </UFormGroup>

      <UButton type="submit" size="xl" block color="primary">
        Continue
      </UButton>
    </UForm>

    <UButton type="submit" size="xl" color="primary" variant="link" block>
      Don't have an account? Sign up
    </UButton>
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
