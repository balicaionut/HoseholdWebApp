<template>
  <div class="checklist">
    <ChecklistTodoCompVue 
      :text="text"
    />
  </div>
</template>

<script>

import ChecklistTodoCompVue from '@/components/ChecklistTodoComp.vue'

export default {
  name: 'ChecklistsView',
  components: {
    ChecklistTodoCompVue,
  },
  data() {
    return {
        text: "To Do List"
    }
  }
}
</script>