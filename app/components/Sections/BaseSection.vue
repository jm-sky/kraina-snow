<script setup lang="ts">
import { cn } from '~/lib/utils';

defineProps<{
  title: string
  contentClass?: string
}>()
</script>

<template>
  <section class="py-20 bg-white dark:bg-gray-900">
    <div class="container mx-auto px-4">
      <h2 class="text-4xl font-bold text-center mb-12 border-b-4 border-primary pb-2 w-fit mx-auto">
        {{ title }}
      </h2>
      <div :class="cn('grid md:grid-cols-3 gap-8', contentClass)">
        <slot />
      </div>
    </div>
  </section>
</template>
