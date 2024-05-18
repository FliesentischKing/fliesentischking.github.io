<script setup lang="ts">
import { Icon } from '@iconify/vue'
import { Button } from '@/components/ui/button'
import { DropdownMenu, DropdownMenuContent, DropdownMenuItem, DropdownMenuTrigger } from '@/components/ui/dropdown-menu'

const colorMode = useColorMode()

const switchColorMode = () => {

  if(colorMode.preference === 'light')
  {
    colorMode.preference = 'dark'
  } 
  else
  {
    colorMode.preference = 'light'
  }
}
</script>

<template>
      <Button @click="switchColorMode()" variant="outline">
        <Icon icon="radix-icons:sun" class="h-[1.2rem] w-[1.2rem] rotate-0 scale-100 transition-all dark:-rotate-90 dark:scale-0" />
        <Icon icon="radix-icons:moon" class="absolute h-[1.2rem] w-[1.2rem] rotate-90 scale-0 transition-all dark:rotate-0 dark:scale-100" />
        <span class="sr-only">Theme ändern</span>
      </Button>
</template>