<template>
    <div>
      <quest-details></quest-details>
      <quest-objectives></quest-objectives>
    </div>
</template>

<script>
import QuestDetails from '@/components/QuestView/QuestDetails.vue'
import QuestObjectives from '@/components/QuestView/QuestObjectives.vue'

export default {
  name: 'QuestView',
  components: {
    QuestDetails,
    QuestObjectives
  }
}
</script>

<style scoped>
div{
    background-color:thistle;
}
</style>
