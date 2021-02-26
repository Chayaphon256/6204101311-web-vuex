<template>
  <div class="about">
    <div class="text-danger">
      กรุณากดconfirmเพื่อดำเนินการชำระสินค้า
    </div>
    <div class="row">
      <product
        v-for="(item, index) in SearchMenu"
        :key="index"
        :NameProduct="item.NameProduct"
        :img="item.img"
        :Price="item.Price"
        :id="index"
        
      />
    </div>
  </div>
</template>
<script>
import Product from "../components/Product.vue";
import {mapGetters} from "vuex";
export default {
  name: "Home",
  components: {
    Product,
  },
  computed: {
    ...mapGetters(["SearchMenu"]),
  
 /* components: { Product },
  props: {
    Menuitem: Array
  },
  data() {
    return {
      select: []
    };
  },
  methods: {
    menuorder(value) {
      this.select.push(value);
      this.$emit("Order", this.select);
    }*/
  }
};
</script>