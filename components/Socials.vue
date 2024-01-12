<script setup lang="ts">
import { Button } from '@/components/ui/button'
import { socialList } from "~/contents/socialList";
import { openLink } from "~/lib/utils";
</script>

<template>
  <div>

    <Button
        v-for="social in socialList"
        class="mr-2 dark:bg-gray-50/10 dark:hover:bg-gray-50/30 text-foreground bg-gray-500/10 hover:bg-gray-500/30 shadow-none"
        :text="social.text"
        :href="social.link"
        :icon="social.icon"
        @click="openLink(social.link)"
    >
        <Icon :name="social.icon" />
        <div class="ml-1" v-if="social.text">{{ social.text }}</div>
    </Button>
  </div>

</template>

<style scoped>

</style>
