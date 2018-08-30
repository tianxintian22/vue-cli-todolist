<template>
  <div>
    <div>
      <input v-model="inputValue"/>
      <button @click="handleSubmit">提交</button>
    </div>
    <ul>
      <todo-item
              v-for="(item, index) in list"
              :key="index"
              :value="item"
              :index="index"
              @delete="handleDelete"
      ></todo-item>
    </ul>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  components: {
    'todo-item': HelloWorld
  },
    data: function() {
        return {
            inputValue: '',
            list: []
        }
    },
    methods: {
        handleSubmit: function () {
            this.list.push(this.inputValue);
            this.inputValue = ''
        },
        handleDelete: function (index) {
            this.list.splice(index, 1)
        }
    }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
