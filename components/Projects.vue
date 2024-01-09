<script setup lang="ts">
import {Collapsible, CollapsibleContent, CollapsibleTrigger} from "~/components/ui/collapsible";
import ProjectItem from "~/components/custom/project-item/ProjectItem.vue";
import {defaultProjectList} from '@/contents/projectList'
import {extendedProjectList} from "@/contents/projectList";

const isOpen = ref(false)
</script>

<template>
  <Collapsible
      v-model:open="isOpen"
      class="mt-10"
  >
    <div class="flex items-center justify-between">
      <h4 class="text-3xl font-semibold tracking-tight transition-colors first:mt-0 hover:no-underline border-b">
        Projects
      </h4>
      <CollapsibleTrigger as-child>
        <Icon name="system-uicons:chevron-close" class="h-6 w-6"/>
      </CollapsibleTrigger>
    </div>

    <ProjectItem
        v-for="project in defaultProjectList"
        class="mt-2"
        :name="project.name"
        :icon="project.icon"
        :desc="project.desc"
        :href="project.link"
    />

    <CollapsibleContent>
      <ProjectItem
          v-for="project in extendedProjectList"
          class="mt-2"
          :name="project.name"
          :icon="project.icon"
          :desc="project.desc"
          :href="project.link"
      />
    </CollapsibleContent>
  </Collapsible>
</template>

<style scoped>

</style>
