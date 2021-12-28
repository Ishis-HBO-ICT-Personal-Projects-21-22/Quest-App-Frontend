<template>
    <div id="quest-nav-styling">
      <quest-line></quest-line>
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
  methods: {
    addquestline () {
      console.log('yes')
    }
  }
}
</script>

<style>
#add-questline-button{
  cursor: pointer;
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
