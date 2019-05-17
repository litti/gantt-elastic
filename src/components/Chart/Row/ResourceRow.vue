<template>
  <g class="gantt-elastic__chart-row-wrapper" :style="{ ...root.style['chart-row-wrapper'] }">
    <template v-for="task in root.visibleTasks" v-if="task.resourceId === resource.id">
      <component :task="task" :is="task.type"></component>
    </template>
  </g>
</template>

<script>
  import Task from './Task.vue';
  import Milestone from './Milestone.vue';
  import Project from './Project.vue';

  export default {
    name: "ResourceRow",
    components: {
      Task,
      Milestone,
      Project,
    },
    props: ['resource'],
    inject: ['root'],
  }
</script>
