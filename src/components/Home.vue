<template>
  <div class="container mt-4">
    <h1>รายรับ-รายจ่าย</h1>
    <Table v-bind:taskList="taskList"/>
    <Total v-bind:taskList="taskList"/>
    <Form v-bind:addTaskList="addTaskList" />
  </div>
</template>

<script>
import Table from "../components/Table/Table.vue";
import Form from "../components/Form/Form.vue";
import Total from "../components/Form/Total.vue";
//import dummy from "../dummy.json"

export default {
  components: {
    Table: Table,
    Form: Form,
    Total: Total
  },
  created(){
    //import json file
    //let newTaskList = [...dummy.taskList];
    //this.taskList = newTaskList;
  },
  data() {
    return {
      taskList: [],
    };
  },
  methods: {
    addTaskList(task) {
      let newTaskList = [...this.taskList, task];
      this.taskList = newTaskList;
    },
  },
};
</script>
