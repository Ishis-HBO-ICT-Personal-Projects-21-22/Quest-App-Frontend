<template>
    <div>
      <h2>{{title}}</h2>
      <br>
      <div @dblclick="changeDescription" @blur="changeDescription" class="description">
        <textarea :disabled=descriptionDisabled v-model="currentDescription"> </textarea>
      </div>
    </div>
</template>

<script>

export default {
  name: 'QuestDetails',
  props: {
    title: null,
    description: null
  },
  data () {
    return {
      currentTitle: '',
      currentDescription: '',
      descriptionDisabled: true
    }
  },
  methods: {
    changeDescription () {
      this.descriptionDisabled = !this.descriptionDisabled
    }
  }
}
</script>

<style scoped>
h2{
  margin:0px;
}
.description{
  border: 1px solid black;
  height: 180px;
}
textarea{
  background-color: transparent;
  height:100%;
  width:100%;
  border: none;
  overflow: auto;
  outline: none;
  resize: none;
  -webkit-box-shadow: none;
  -moz-box-shadow: none;
  box-shadow: none;
}
textarea .disabled{
  color:black;
  pointer-events: auto;
}
</style>
