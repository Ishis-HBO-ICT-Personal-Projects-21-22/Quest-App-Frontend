<template>
    <div id="quest-nav-styling">
      <quest-line class="quest-line-styling" v-for="questline in questsLines"
      :key = "questline.id"
      :id = "questline.id"
      :title = "questline.title"
      :quests = "questline.quests"
      @questSelected = questSelected
      >
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
  props: {
    quests: {
      type: Array,
      default () { return [] }
    }
  },
  data () {
    return {
      questsLines: []
    }
  },
  methods: {
    init () {
      // get quests
      this.questsLines = this.quests
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
    },
    questSelected (id) {
      this.$emit('questSelected', id)
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
  margin-top:30px;
  text-align: center;
}

.quest-nav-title{
  text-align: left;
  border: 1px solid black;
  border-left: 0px;
  padding:10px;
  margin: 0 0 0 auto;
  width:calc(100% - 20px);
  cursor: pointer;
}

.quest-nav{
  border-top: 0px;
  border-right:0px;
  border-left: 1px solid black;
  width:85%;
}

.quest-line-styling{
  margin-top:20px;
}
</style>
