<template>
  <div class="main-container center">
    <quest-nav></quest-nav>
    <quest-view></quest-view>
  </div>
</template>

<script>
import QuestNav from '@/components/QuestNav.vue'
import QuestView from '@/components/QuestView.vue'

export default {
  name: 'QuestLog',
  components: {
    QuestNav,
    QuestView
  },
  props: { }
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
