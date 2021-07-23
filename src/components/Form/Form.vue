<template>
  <div class="card mt-4">
    <div class="card-body">
      <h4 class="card-title">เพิ่มข้อมูล</h4>

      <div class="mb-3">
        <label for="name" class="form-label">รายการ</label>
        <input type="text" class="form-control" id="name" v-model="name" />
      </div>

      <div class="mb-3">
        <label for="price" class="form-label">จำนวน</label>
        <input
          type="text"
          class="form-control"
          id="price"
          placeholder="หน่วยเป็นบาท"
          v-model="price"
        />
      </div>

      <label for="dateInput" class="me-3">วันที่ : </label>
      <input type="date" id="dateInput" ref="dateInput" />

      <label for="typeInput" class="mx-3">ประเภท : </label>
      <select id="typeInput" ref="typeInput">
        <option value="รายรับ">รายรับ</option>
        <option value="รายจ่าย">รายจ่าย</option>
      </select>
    </div>
    <div class="card-footer">
      <button
        class="btn btn-success"
        style="float: right"
        v-on:click="handleAddBtn"
      >
        เพิ่มรายการ
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      type: "",
      price: "",
      date: "",
    };
  },

  methods: {
    handleAddBtn() {
      if (!this.$refs.dateInput.value || !this.name || !this.price) {
        alert("กรุณาใส่ข้อมูลให้ครบ");
      } else {
        this.type = this.$refs.typeInput.value;
        this.date = this.$refs.dateInput.value;
        console.log(`${this.name}/${this.price}/${this.type}/${this.date}`);

        let task = {
          name: this.name,
          price: this.price,
          date: this.date,
          type: this.type,
        };

        this.addTaskList(task);
      }
    },
  },

  props: ["addTaskList"],
};
</script>
