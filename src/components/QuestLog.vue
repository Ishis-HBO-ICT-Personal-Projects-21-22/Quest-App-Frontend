<template>
  <div class="main-container center">
    <quest-nav
    ref="questnav"
    :quests = currentQuests
    @questSelected = questSelected
    ></quest-nav>
    <quest-view
    ref="questview"
    :selectedQuest = selectedQuest
    ></quest-view>
  </div>
</template>

<script>
import QuestNav from '@/components/QuestNav/QuestNav.vue'
import QuestView from '@/components/QuestView/QuestView.vue'

export default {
  name: 'QuestLog',
  components: {
    QuestNav,
    QuestView
  },
  props: {
    quests: {
      type: Array,
      default () {
        return []
      }
    }
  },
  data () {
    return {
      currentQuests: [],
      selectedQuest: {}
    }
  },
  methods: {
    async init () {
      // get quest request
      this.currentQuests = this.quests
      if (this.currentQuests.length === 0) {
        this.currentQuests = [{
          id: 1,
          title: 'Quest Line 1',
          quests: [{
            id: 1001,
            index: 1,
            title: 'Quest 1',
            description: '',
            objectives: [{
              title: 'objective 1'
            }]
          },
          {
            id: 1002,
            index: 2,
            title: 'Quest 2',
            description: '',
            objectives: [{
              title: 'objective 1'
            }]
          }]
        }]
      }
      this.selectedQuest = this.currentQuests[0].quests[0]
    },
    questSelected (id) {
      this.selectedQuest = this.currentQuests.map(questLine => questLine.quests)[0]
        .filter(quest => quest.id === id)[0]
      this.$refs.questview.init()
    }
  },
  mounted () {
    // await this.init()
    this.init().then((result) => {
      this.$refs.questnav.init()
    }).then((result) => this.$refs.questview.init())
  }
}
</script>

<style scoped>
.main-container{
  border: 2px solid black;
  height: 650px;
  display:grid;
  grid-template-columns:1fr 2.5fr;
}
.center {
  margin: auto;
  width: 70%;
}
</style>
