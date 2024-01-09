<template>
  <div class="px-6 py-[15vh] max-w-[76ch] mx-auto xl:text-lg">
    <h1 class="scroll-m-20 text-4xl font-extrabold tracking-tight lg:text-5xl">
      Hi,
    </h1>
    <h1 class="scroll-m-20 text-4xl font-extrabold tracking-tight lg:text-5xl">
      I'm qwerzl
    </h1>
    <p class="leading-7 text-neutral-300 mt-6 text-[16px]">
      CG&CS Enthusiast.
    </p>
    <p class="text-neutral-300 text-[16px]">
      WFLA '25, Computerization '24.
    </p>
    <Socials class="mt-3"/>

    <Projects class="mt-10"/>

<!--    <Accordion type="single" collapsible default-value="item-1" class="mt-10">-->
<!--      <AccordionItem value="item-1">-->
<!--        <AccordionTrigger-->
<!--            class="text-3xl font-semibold tracking-tight transition-colors first:mt-0 hover:no-underline">-->
<!--          Is it accessible?-->
<!--        </AccordionTrigger>-->
<!--        <AccordionContent>-->
<!--          Yes. It adheres to the WAI-ARIA design pattern.-->
<!--        </AccordionContent>-->
<!--      </AccordionItem>-->
<!--    </Accordion>-->


  </div>
</template>
<script lang="ts" setup>
// Import utils
import { useDark } from "@vueuse/core";

// Import Components
import { Accordion, AccordionContent, AccordionItem, AccordionTrigger } from '@/components/ui/accordion'
import Projects from "~/components/Projects.vue";



const isDark = useDark();
// useHead composable to add CSS class in the HTML body
// when it is dark mode
useHead({
  bodyAttrs: {
    class: computed(() => {
      if (isDark) return 'dark';
      return '';
    }),
  },
});
</script>
