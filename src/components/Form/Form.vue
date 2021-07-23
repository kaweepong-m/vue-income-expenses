<template>
  <div class="card mt-4 p-3">
    <div class="card-body">
      <h1 class="card-title">เพิ่มข้อมูล</h1>
      <div class="mb-3">
        <label for="name" class="form-label">รายการ</label>
        <input type="text" class="form-control" id="name" />
      </div>
      <div class="mb-3">
        <label for="price" class="form-label">จำนวน</label>
        <input type="text" class="form-control" id="price" />
      </div>
      <div class="dropdown">
        <button
          class="btn btn-secondary dropdown-toggle"
          type="button"
          id="dropdownMenuButton1"
          data-bs-toggle="dropdown"
          aria-expanded="false"
        >
          ประเภท
        </button>
        <ul class="dropdown-menu" aria-labelledby="dropdownMenuButton1">
          <li><a class="dropdown-item" href="#">Action</a></li>
          <li><a class="dropdown-item" href="#">Another action</a></li>
        </ul>
      </div>
      <div class="mt-3">
          <button class="btn btn-success">เพิ่มรายการ</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>
</style>