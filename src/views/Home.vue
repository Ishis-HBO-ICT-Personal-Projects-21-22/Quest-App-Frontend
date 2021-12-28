<template>
  <div class="home">
    <h1>Quest Log </h1>
    <quest-log id="quest-log"></quest-log>
  </div>
</template>

<script>
import QuestLog from '@/components/QuestLog.vue'

export default {
  name: 'Home',
  components: {
    QuestLog
  }
}
</script>

<style scoped>
</style>
