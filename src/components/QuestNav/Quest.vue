<template>
    <div class="quest-nav-title quest-nav" @click="questSelected"> {{title}} </div>
</template>

<script>

export default {
  name: 'Quest',
  props: {
    id: null,
    title: null,
    index: null
  },
  methods: {
    questSelected () {
      console.log(this.id)
      console.log(this.title)
      console.log(this.index)
    }
  }

}
</script>

<style scoped>
</style>
