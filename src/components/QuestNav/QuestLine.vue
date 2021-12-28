<template>
    <div>
        <quest-line-title :title = title></quest-line-title>
        <div>
          <quest v-for="quest in currentQuests"
          :key="quest.id"
          :id="quest.id"
          :title="quest.title"
          :index="quest.index">
          </quest>
        </div>
        <div id="add-quest-button" class="quest-nav-title quest-nav" @click="addquest">+</div>
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
      console.log(this.title)
      this.currentQuests = this.quests
    },
    addquest () {
      const nextId = Math.max(...this.currentQuests.map(quest => quest.id)) + 1
      const nextIndex = Math.max(...this.currentQuests.map(quest => quest.index)) + 1
      this.currentQuests.push({
        id: nextId,
        title: 'Quest ' + nextIndex,
        index: nextIndex
      })
    }
  },
  mounted () {
    this.init()
  }
}
</script>

<style scoped>
#add-quest-button{
  padding:5px 10px;
  height:15px;
}
</style>
