<template>
  <div class="home">
    <user/>
    <table class="table">
      <thead class="thead-dark">
        <tr>
          <th scope="col">ชื่อสินค้า</th>
          <th scope="col">ราคา</th>
          <th scope="col">จำนวน</th>
          <th scope="col">รวม</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(mi, index) in ShowMenuSelect" :key="index">
          <td>{{ mi.NameProduct }}</td>
          <td>{{ mi.Price }}</td>
          <td>{{ mi.Amount }}</td>
          <td>{{ mi.Total }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import user from "../components/User.vue";
import {mapGetters} from "vuex";

export default {
  name: "Home",
  components: {
    user
  },
    computed: {
      ...mapGetters(["ShowMenuSelect"]),

  },
};
</script>
