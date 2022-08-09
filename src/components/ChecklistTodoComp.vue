<template>
  <div class="checklist">
    <div v-for="item in todoList" :key="item">
      <div v-if="item.isDone" >
        <input type="checkbox" id="item.id" name="item.id" checked>
        <label v-if="item.isDone"  for="item.id"><s>{{ item.textField }}</s></label>
      </div>
      <div v-else>
        <input type="checkbox" id="item.id" name="item.id">
        <label for="item.id">{{ item.textField }}</label>
      </div>

    </div>
  </div>
</template>

<script>

export default {
  name: 'ChecklistTodoComp',
  components: {

  },
  props: ['text'],
  setup() {
    const todoList = [
        {
          id: 1, isDone: false, textField: "test 1", dateCreated: "1659447034", dueDate: ""
        },
        {
          id: 2, isDone: true, textField: "test 2", dateCreated: "1659437034", dueDate: ""
        },
        {
          id: 3, isDone: false, textField: "test 3", dateCreated: "1659427034", dueDate: "1659477034"
        }
      ]

    const timestamp = 1659447034

    var date = unixToDate(timestamp)

    var unixTime = dateToUnix(date)

    // var list = parseTodoList(todoList)

    function unixToDate (data) {
        data = new Date(data * 1000)
      return data
    }

    function dateToUnix (data) {
        data = data.getTime() / 1000
      return data
    }

    // function parseTodoList(data) {
    //   data = JSON.parse(data)
    //   return data
    // }



    return {
      date,
      unixTime,
      todoList,
      // list
    }
  },
  data() {
    return {
      
    }
  }
}
</script>