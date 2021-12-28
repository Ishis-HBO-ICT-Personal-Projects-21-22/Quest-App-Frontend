<template>
    <div>
        <quest-line-title></quest-line-title>
        <div>
          <quest v-for="quest in currentQuests"
          :key="quest.id"
          :title="quest.title"
          >
          </quest>
        </div>
    </div>
</template>

<script>
import Quest from '@/components/QuestNav/Quest.vue'
import QuestLineTitle from '@/components/QuestNav/QuestLineTitle.vue'

export default {
  name: 'QuestLine',
  components: {
    QuestLineTitle,
    Quest
  },
  props: {
    id: null,
    title: null,
    quests: {
      type: Array,
      default () {
        return []
      }
    }
  },
  data () {
    return {
      currentQuests: []
    }
  },
  methods: {
    async init () {
      this.currentQuests = this.quests
    }
  },
  mounted () {
    this.init()
  }
}
</script>

<style scoped>
</style>
