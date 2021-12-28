<template>
    <div class="objective-block">
      <h3>{{currentTitle}}</h3>
    </div>
</template>

<script>

export default {
  name: 'Objective',
  props: {
    title: null
  },
  data () {
    return {
      currentTitle: ''
    }
  },
  methods: {
    async init () {
      this.currentTitle = this.title
      console.log(this.currentTitle)
    }
  },
  mounted () {
    this.init()
  }
}
</script>

<style scoped>
h3{
  margin:0px;
}
.objective-block{
  border:1px solid black;
  padding:10px 15px;
  text-align: left;
}
</style>
