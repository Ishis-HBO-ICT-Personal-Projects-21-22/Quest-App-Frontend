<template>
    <div id="quest-nav-styling">
      <quest-line class="quest-line-styling" v-for="questline in questsLines"
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
            id: 1001, title: 'Quest 1', index: 1
          },
          {
            id: 1002, title: 'Quest 2', index: 2
          }]
        }]
      }
      console.log(this.questsLines[0])
    },
    addquestline () {
      const nextId = Math.max(...this.questsLines.map(questLine => questLine.id)) + 1
      this.questsLines.push({
        id: nextId,
        title: 'Quest Line ' + nextId,
        quests: [{
          id: nextId + '00' + 1, title: 'Quest 1', index: 1
        }]
      })
    }
  },
  mounted () {
    this.init()
  }
}
</script>

<style>
#quest-nav-styling{
  border-right: 2px solid black;
}
#add-questline-button{
  cursor: pointer;
  margin-top:30px;
  text-align: center;
}
.quest-nav-title{
  text-align: left;
  border: 1px solid black;
  padding:10px;
  margin: 0 0 0 auto;
  width:calc(100% - 20px);
}
.quest-nav{
  border-top: 0px;
  width:80%;
}

.quest-line-styling{
  margin-top:20px;
}
</style>
