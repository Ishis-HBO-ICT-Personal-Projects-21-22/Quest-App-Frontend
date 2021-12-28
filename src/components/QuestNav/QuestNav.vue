<template>
    <div id="quest-nav-styling">
      <quest-line v-for="questline in questsLines"
      :key = "questline.id"
      :id = "questline.id"
      :title = "questline.title"
      :quests = "questline.quests">
      </quest-line>
      <div id="add-questline-button" class="quest-nav-title" @click="addquestline">+</div>
    </div>
</template>

<script>
import QuestLine from '@/components/QuestNav/QuestLine.vue'

export default {
  name: 'QuestNav',
  components: {
    QuestLine
  },
  data () {
    return {
      questsLines: []
    }
  },
  methods: {
    async init () {
      // get quests
      if (this.questsLines.length === 0) {
        this.questsLines = [{
          id: 1,
          title: 'Quest Line 1',
          quests: [{
            id: 1, title: 'quest 1'
          },
          {
            id: 2, title: 'quest 2'
          }]
        }]
      }
    },
    addquestline () {
      console.log('yes')
    }
  },
  mounted () {
    this.init()
  }
}
</script>

<style>
#add-questline-button{
  cursor: pointer;
  margin-top:30px;
}
#quest-nav-styling{
  border-right: 2px solid black;
  padding: 20px 10px;
}
.quest-nav-title{
  border: 1px solid black;
  padding:10px;
}
.quest-nav{
  border-top: 0px;
}
</style>
