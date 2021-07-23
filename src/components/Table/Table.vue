<template>
  <div>
    <table class="table table-light table-striped table-hover mt-3">
      <thead>
        <tr>
          <th scope="col">ลำดับ</th>
          <th scope="col">รายการ</th>
          <th scope="col">ประเภท</th>
          <th scope="col">จำนวน(บาท)</th>
          <th scope="col">วันที่ทำรายการ</th>
        </tr>
      </thead>
      <tbody>
        <TableMember
          v-for="(task, index) in taskList"
          :key="index"
          v-bind:data="task"
          v-bind:index="index + 1"
        />
      </tbody>
    </table>
  </div>
</template>

<script>
import TableMember from "./TableMember.vue";

export default {
  props: ["taskList"],

  components: {
    TableMember: TableMember,
  },
};
</script>
