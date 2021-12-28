<template>
    <div>
      <h2>Objectives</h2>
      <div>
        <objective v-for="objective in currentObjectives"
        :key = "objective.id"
        :title = "objective.title"
        ></objective>
      </div>
    </div>
</template>

<script>
import Objective from '@/components/QuestView/Objective.vue'

export default {
  name: 'QuestObjectives',
  components: {
    Objective
  },
  props: {
    objectives: {
      type: Array,
      default () {
        return []
      }
    }
  },
  data () {
    return {
      currentObjectives: []
    }
  },
  methods: {
    async init () {
      this.currentObjectives = this.objectives
      console.log(this.objectives[0].title)
    }
  },
  mounted () {
    console.log(this.objectives)
  }
}
</script>

<style scoped>
</style>
