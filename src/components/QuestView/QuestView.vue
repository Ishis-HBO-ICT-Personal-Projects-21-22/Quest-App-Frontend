<template>
    <div id="questview">
      <quest-details
      :title = selectedQuest.title
      :description = selectedQuest.description
      ></quest-details>
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
  },
  props: {
    selectedQuest: null
  },
  methods: {
    async init () {}
  },
  mounted () {
    this.init()
  }
}
</script>

<style scoped>
#questview{
  padding:10px;
}
</style>
