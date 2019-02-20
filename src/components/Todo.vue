<template>
  <div class="hello">
    <input v-model="task">
    <ul>
      <li v-for="(item, i) in tasks" :key="i">{{ item }}<button @click="deleteTask(item)">Удалить</button></li>
    </ul>
    <button @click="push">Добавить</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld', 
  data() {
    return {
      task: '',
      tasks: []
    }
  },
  methods: {
    push() {
      if(this.task !== '') {
          this.tasks.push(this.task)
          this.task = ''
      }
    },
    deleteTask(item) {
      this.tasks = this.tasks.filter((data) => data !== item)
    } 
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>

</style>
