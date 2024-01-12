<script setup lang="ts">
import { cn } from '@/lib/utils'

const props = defineProps({
  href: {
    type: String,
    default: '',
  },
  class: {
    type: String,
    default: ''
  },
  text: {
    type: String,
    default: ''
  },
  icon: {
    // icon names from https://icones.js.org/
    type: String,
    default: ''
  }
})
</script>

<template>
  <a
      :class="
        cn(
          'inline-flex px-3 py-2 mt-2 mr-2 rounded-md transition-colors decoration-none hover:text-white dark:bg-gray-50/10 bg-black text-white',
          props.class
        )
      "
      :href="props.href"
      target="_blank"
  >
    <Icon :name="props.icon" />
    <div class="text-sm ml-1" v-if="props.text">{{ props.text }}</div>
  </a>
</template>

<style scoped>

</style>
