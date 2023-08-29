<script setup>
import ListItem from './components/ListItem.vue';
import { ref } from 'vue'

const list = ref([{ desc: 'Complete task 2-1c' }, { desc: 'Go to the gym' }])

function createtask(taskdesc) {
  this.list.push({desc: taskdesc});
}

const newtask = ref('')

</script>

<template>
  <header class="wrapper">
    <div>
      <h1>ToDo List</h1>

      <h2>Add an item?</h2>
      <input v-model="newtask" placeholder="New task description"/>
      <button @click="createtask(newtask)">Add to list</button>
      <div class="help">
        <p>Press the green tick next to a task to mark it as complete.</p>
        <p>Press the red button on a complete task to remove it from the list.</p>
        <p>You can undo completion of a task by pressing the green tick again.</p>
      </div>
    </div>
  </header>

  <main>
    <ListItem v-for="item in list" :task="item.desc"/>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}

h1 {
  color: greenyellow;
}

button{
  display: inline-block;
  vertical-align: middle;
  background-color: #aaa;
  border: none;
  color: white;
  padding: 5px 5px;
  text-align: center;
  text-decoration: none;
  font-size: 16px;
  border-top-right-radius: 5px;
  border-bottom-right-radius: 5px;
  }

input{
  display: inline-block;
  vertical-align: middle;
  background-color: #ddd;
  border: none;
  color: black;
  padding: 5px 5px;
  text-align: center;
  text-decoration: none;
  font-size: 16px;
  border-top-left-radius: 5px;
  border-bottom-left-radius: 5px;
  }

.help {
  margin-top: 15px;
}
</style>
