<template>
  <div id="project-list">
    <h5>{{ heading }}</h5>
    <ProjectCard
      v-for="project in projects"
      :key="project.id"
      :project="project"
    />
  </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';
import ProjectCard from './ProjectCard.vue'
import ProjectInterface from '@/interfaces/Project'

export default defineComponent({
  name: 'ProjectList',
  components: {
    ProjectCard,
  },
  props: {
    heading: {
      type: String,
      required: true,
    },
    projects: {
      type: Array as PropType<ProjectInterface[]>,
      required: true,
    },
  },
})
</script>

<style lang="scss">
#project-list {
  display: flex;
  flex-direction: column;
  padding: 20px;
  min-width: 280px;
  background-color: #f4f6f8;

  & > h5 {
    text-align: left;
    color: #c0c2c4;
  }

  & > #project-card:not(:first-of-type) {
    margin-top: 20px;
  }
}
</style>
