<template>
<div class="container mt-4">
  <h1>รายรับ-รายจ่าย</h1>
  <Table/>
  <Form/>


</div>

</template>

<script>
import Table from '../components/Table/Table.vue'
import Form from '../components/Form/Form.vue'
export default {
  props: {
    msg: String
  },
  components:{
    Table: Table,
    Form: Form
  }
}
</script>
