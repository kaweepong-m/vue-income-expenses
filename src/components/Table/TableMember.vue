<template>
    <tr class="table table-light">
      <th scope="row">{{index}}</th>
      <td>{{data.name}}</td>
      <td v-if="data.type === `รายรับ`" style="color : green" >{{data.type}}</td>
      <td v-else style="color : red">{{data.type}}</td>
      <td>{{data.price}}</td>
      <td>{{data.date}}</td>
    </tr>
</template>

<script>
export default {
  props : ["data","index"]
};
</script>
