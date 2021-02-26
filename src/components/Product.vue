<template>
  <div class="col-lg-3">
    <b-card
      border-variant="warning"
      :header="NameProduct"
      header-bg-variant="dark"
      header-text-variant="white"
      align="center"
      style="height: 40rem"
      ><b-col md="12">
        <b-card-img :src="img" alt="Image" class="rounded-0"></b-card-img>
      </b-col>
      <b-card-text>ราคา : {{ Price }} บาท</b-card-text>
      จำนวน
      <b-form-spinbutton
        id="sb-small"
        size="sm"
        v-model="Amount"
        class="mb-2"
      ></b-form-spinbutton>
      <button type="button" class="btn btn-outline-info" @click="Order(Amount,id)">
        <b-icon icon="basket"></b-icon> หยิบใส่
      </button>
    </b-card>
  </div>
</template>
<script>
import { mapGetters } from 'vuex';
export default {
  props: {
    NameProduct: String,
    img: String,
    Price: Number,
    id: Number
  },
  data() {
    return {
      Amount: 1,
    }
  },

  computed: {
    ...mapGetters(["Order"]),
  },
 /* methods: {
    Order() {
      alert("หยิบสินค้าเรียบร้อย");
      this.$emit("Order", {
        NameProduct: this.NameProduct,
        Price: this.Price,
        Amount: this.Amount,
        Total: this.Price * this.Amount
      });
    }
  },*/
};
</script>

