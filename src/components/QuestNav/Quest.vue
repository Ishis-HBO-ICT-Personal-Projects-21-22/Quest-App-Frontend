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
      this.$emit('questSelected', this.id)
    }
  }

}
</script>

<style scoped>
</style>
