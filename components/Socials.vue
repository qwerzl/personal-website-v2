<script setup lang="ts">
import { SocialButton } from "@/components/custom/social-button";

import { socialLists } from "@/contents/socialLists";

</script>

<template>
  <div>
    <SocialButton
        v-for="social in socialLists"
        :class="social.class"
        :text="social.text"
        :href="social.link"
        :icon="social.icon"
    />
  </div>

</template>

<style scoped>

</style>
