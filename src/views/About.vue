<template>
  <div class="about">
    <div class="row">
      <card
        v-for="(car, index) in Menuitem"
        :key="index"
        :NameProduct="car.NameProduct"
        :img="car.img"
        :Price="car.Price"
        @Order="menuorder"
      />
    </div>

    <total :Total="Total" :Data="Data" />
    <table class="table">
      <thead class="thead-yyy">
        <tr>
          <th scope="col">img</th>
          <th scope="col">Product</th>
          <th scope="col">Price</th>
          <th scope="col">Unit</th>
          <th scope="col">Total</th>
        </tr>
      </thead>
      <tbody class="text-white">
        <tr v-for="(ca, index) in Data" :key="index">
          <td>{{ ca.img }}</td>
          <td>{{ ca.NameProduct }}</td>
          <td>{{ ca.Price }}</td>
          <td>{{ ca.Amount }}</td>
          <td>{{ ca.Total }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
// @ is an alias to /src
import Total from "../components/Total.vue";

export default {
  name: "About",
  components: {
    Total
  },
  props: {
    Total: Number,
    Data: Array,
    Menuitem: Array,
  },
  data() {
    return {};
  },
  methods: {
    menuorder(value) {
      this.select.push(value);
      this.$emit("Order", this.select);
    }
  }
};
</script>
<style>
.table .thead-yyy th {
  color: rgb(0, 0, 0);
  background-color: #e1fa00;
  border-color: #000000;
}
.bg-black {
  color: #000;
}
</style>
