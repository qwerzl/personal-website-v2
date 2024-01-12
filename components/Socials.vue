<script setup lang="ts">
import { SocialButton } from "@/components/custom/social-button";
import { Button } from '@/components/ui/button'
import { socialLists } from "@/contents/socialLists";

</script>

<template>
  <div>

    <Button
        v-for="social in socialLists"
        class="mr-2 dark:bg-gray-50/10 text-foreground bg-gray-500/10 shadow-none"
        :text="social.text"
        :href="social.link"
        :icon="social.icon"
    >
        <Icon :name="social.icon" />
        <div class="ml-1" v-if="social.text">{{ social.text }}</div>

    </Button>
  </div>

</template>

<style scoped>

</style>
