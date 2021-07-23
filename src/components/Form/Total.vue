<template>
  <div class="card mt-4">
    <div class="card-body">
      <h4>สรุปรายรับ-รายจ่าย</h4>
      <p>
        รายรับทั้งหมด : <strong>{{ this.totalIn }}</strong>
      </p>
      <p>
        รายจ่ายทั้งหมด : <strong>{{ this.totalEx }}</strong>
      </p>
    </div>
    <div class="card-footer">
      <h5>ยอดรวม : {{ this.total }}</h5>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      totalIn: 0,
      totalEx: 0,
      total: 0,
    };
  },
  props: ["taskList"],

  created() {
    this.taskList.map((task) => {
      if (task.type === "รายรับ") {
        this.totalIn += parseInt(task.price);
      } else {
        this.totalEx += parseInt(task.price);
      }

      this.total = this.totalIn - this.totalEx;
    });
  },

  watch: {
    taskList: function (newVal) {
      let sumIn = 0;
      let sumEx = 0;
      let total = 0;

      newVal.map((task) => {
        if (task.type === "รายรับ") {
          sumIn += parseInt(task.price);
        } else {
          sumEx += parseInt(task.price);
        }

        total = sumIn - sumEx;
      });

      this.totalIn = sumIn;
      this.totalEx = sumEx;
      this.total = total;
    },
  },
};
</script>