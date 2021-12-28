<template>
    <div>
        <objective></objective>
    </div>
</template>

<script>
import Objective from '@/components/QuestView/Objective.vue'

export default {
  name: 'QuestObjectives',
  components: {
    Objective
  }
}
</script>

<style scoped>
div{
    border-right: 2px solid black;
    padding: 20px 10px;
}
</style>
