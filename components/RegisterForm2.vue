<script setup lang="ts">
import { Button } from '@/components/ui/button'
import { Card, CardContent, CardDescription, CardHeader, CardTitle } from '@/components/ui/card'
import { Input } from '@/components/ui/input'
import { Label } from '@/components/ui/label'
</script>

<template>
  <UiCard class="mx-auto max-w-sm">
    <UiCardHeader>
      <UiCardTitle class="text-xl">
        Registrieren
      </UiCardTitle>
      <UiCardDescription>
        Enter your information to create an account
      </UiCardDescription>
    </UiCardHeader>
    <UiCardContent>
      <div class="grid gap-4">
        <div class="grid grid-cols-2 gap-4">
          <div class="grid gap-2">
            <UiLabel for="first-name">First name</UiLabel>
            <UiInput id="first-name" placeholder="Max" required />
          </div>
          <div class="grid gap-2">
            <UiLabel for="last-name">Last name</UiLabel>
            <UiInput id="last-name" placeholder="Robinson" required />
          </div>
        </div>
        <div class="grid gap-2">
          <UiLabel for="email">Email</UiLabel>
          <UiInput
            id="email"
            type="email"
            placeholder="m@example.com"
            required
          />
        </div>
        <div class="grid gap-2">
          <UiLabel for="password">Password</UiLabel>
          <UiInput id="password" type="password" />
        </div>
        <UiButton type="submit" class="w-full">
          Create an account
        </UiButton>
        <UiButton variant="outline" class="w-full">
          Sign up with GitHub
        </UiButton>
      </div>
      <div class="mt-4 text-center text-sm">
        Already have an account?
        <a href="#" class="underline">
          Sign in
        </a>
      </div>
    </UiCardContent>
  </UiCard>
</template>