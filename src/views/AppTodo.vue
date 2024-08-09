<script setup>
import { ref } from 'vue'
const text = ref('文字文字文字')
const todos = ref([
  {
    text: '範例',
    id: 124
  }
])
const tempEdit = ref({
  text: '',
  id: ''
})
const addTodo = () => {
  //新增文字匡內容至下方資料
  todos.value.push({
    text: text.value,
    id: new Date().getTime()
  })
  console.log(todos.value)
}
const deleteTodo = (item) => {
  console.log(item)
  const index = todos.value.findIndex((todo) => todo.id === item.id)
  console.log(index)
  todos.value.splice(index, 1)
}
const prepareTodo = (item) => {
  tempEdit.value = { ...item } //拷貝技巧:不會被連動
  console.log(tempEdit.value)

  //js傳參考
}
const confirmEdit = () => {
  const index = todos.value.findIndex((todo) => todo.id === tempEdit.value.id)
  console.log(index, todos.value)
  todos.value[index] = tempEdit.value
  tempEdit.value = ''
}
</script>
<template>
  <input type="text" v-model="text" /><button type="button" @click="addTodo">新增</button>
  <br />
  <hr />
  <div v-for="item in todos" :key="item.id">
    {{ item.text }}
    <button type="button" @click="deleteTodo(item)">刪除</button>
    <button type="button" @click="prepareTodo(item)">編輯</button>
    <hr />
  </div>
  <hr />
  <div v-if="tempEdit.id">
    <h1>編輯區</h1>
    現在修改：{{ tempEdit.text }}
    <input type="text" v-model="tempEdit.text" />
    <button type="button" @click="confirmEdit()">確認</button>
    <button type="button" @click="tempEdit = {}">取消</button>
  </div>
</template>

<style></style>
