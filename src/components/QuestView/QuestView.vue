<template>
    <div id="questview">
      <quest-details
      :title = selectedQuest.title
      :description = selectedQuest.description
      ></quest-details>
      <quest-objectives id="overview-questobjectives"
      :objectives = selectedQuest.objectives
      ref="questobjectives"
      ></quest-objectives>
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
    async init () {
      this.$refs.questobjectives.init()
    }
  },
  mounted () {
    this.init()
  }
}
</script>

<style scoped>
#questview{
  padding:20px 10px;
  display:grid;
  grid-template-rows: 40% 60%;
}

#overview-questobjectives{
}
</style>
