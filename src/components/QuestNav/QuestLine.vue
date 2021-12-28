<template>
    <div>
        <quest-line-title></quest-line-title>
        <div>
          <quest v-for="quest in quests"
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
  data () {
    return {
      quests: []
    }
  },
  mounted () {
    this.quests.push({
      id: 1, title: 'quest 1'
    },
    {
      id: 2, title: 'quest 2'
    }
    )
  }
}
</script>

<style scoped>
</style>
