<template>
  <div class="home">
    <b-container>
      <b-row align-v="center">
        <div class="row">
          <card
            v-for="(car, index) in Menuitem"
            :key="index"
            :NameProduct="car.NameProduct"
            :img="car.img"
            :Price="car.Price"
            @Order="menuorder"
          /></div></b-row
    ></b-container>
    <!-- <User></User> -->
  </div>
</template>
<script>
import Card from "@/components/Card.vue";
export default {
  name: "home",
  components: { Card },
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
