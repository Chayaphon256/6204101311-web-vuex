<template>
  <div>
    <div class="card bg-1 mb-3" style="max-width: 120rem">
      <div class="card-header">กรุณากรอกข้อมูล</div>
      <div class="card-body">
        <form>
          <div class="row">
            <div class="col">
              <input
                type="text"
                class="form-control"
                placeholder="ชื่อ"
                v-model="Name"
              />
            </div>
            <div class="col">
              <input
                type="text"
                class="form-control"
                placeholder="เบอร์โทรศัพท์"
                v-model="Tel"
              />
              </div>
              <div class="col">
              <input
                type="text"
                class="form-control"
                placeholder="ที่อยู่"
                v-model="Address"
              />
            </div>
          </div>
        </form>

        <div class="row justify-content-end">
          <h4 class="col-lg-4">ยอดชำระรวม : {{ Total }} บาท</h4>
          <button type="button " class="btn btn-success mr-4" @click="sum()">
            BUY
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import {mapState} from "vuex";
export default {
  computed: { 
    ...mapState(["Total"]),
 
  },
  data() {
    return {
      Name: "",
      Tel: "",
      Address:""
    };
  },
  methods: {
    //ออกบิล
    sum() {
      alert(
        "Name : "+this.Name+
        "Tel : "+this.Tel+
        "Address : "+ this.Address+
        "Total : "+this.Total +
        "฿"
      );
    }
  }
};
</script>

<style scoped>
.bg-1 {
  background-color: rgb(203, 112, 226);
  color: rgb(42, 29, 233);
}
</style>
