<template>
  <div id="app">
    <h1 v-text="title"></h1>
    <ul>
      <li v-for="item in items" v-bind:class="{finished: item.isFinished}" v-on:click="toggleFinish(item)">
        {{ item.label }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data () {
    return {
      title: 'this is a todo list.',
      items: [
        {
          label: 'coding',
          isFinished: false
        },
        {
          label: 'walking',
          isFinished: true
        },
        {
          label: 'eating',
          isFinished: true
        }
      ]
    }
  },
  methods: {
    toggleFinish: function (item) {
      item.isFinished = !item.isFinished
    }
  }

}
</script>

<style>
.finished{
  color: #4df010;
  text-decoration: underline;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2094f4;
  margin-top: 60px;
}
</style>
