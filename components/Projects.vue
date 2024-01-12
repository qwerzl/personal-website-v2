<script setup lang="ts">
import {Collapsible, CollapsibleContent, CollapsibleTrigger} from "~/components/ui/collapsible";
import ProjectItem from "~/components/custom/project-item/ProjectItem.vue";
import {defaultProjectList} from '@/contents/projectList'
import {extendedProjectList} from "@/contents/projectList";

const isOpen = ref(false)
const isShow = ref(false)
</script>

<template>
  <Collapsible
      v-model:open="isOpen"
      class="mt-10"
  >
    <div class="flex items-center justify-between">
      <h4 class="text-3xl font-semibold tracking-tight transition-colors first:mt-0 hover:no-underline border-b border-b-current">
        Projects
      </h4>
      <CollapsibleTrigger as-child>
        <Icon @click="isShow = !isShow" name="system-uicons:chevron-down-circle" class="h-6 w-6 rounded-full toggleUpDown" :class='{ "rotate": isShow }'/>
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
.toggleUpDown {
  transition: transform .3s ease-in-out !important;
}

.toggleUpDown.rotate {
  transform: rotate(180deg);
}
</style>
