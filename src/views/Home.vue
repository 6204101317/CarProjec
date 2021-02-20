<template>
  <div class="about"> 
    <b-container>
      <b-row align-v="center">
        <div class="row">
          <product
            v-for="(item, index) in Menuitem"
            :key="index"
            :NameProduct="item.NameProduct"
            :img="item.img"
            :Price="item.Price"
            @Order="menuorder"
          /></div></b-row
    ></b-container>
    <!-- <User></User> -->
  </div>
</template>
<script>
import Product from "../components/Product.vue";
export default {
  components: { Product },
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
    }
  }
};
</script>
<style></style>