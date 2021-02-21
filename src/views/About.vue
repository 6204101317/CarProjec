<template>
  <div class="about">
    <div class="row">
      <product 
        v-for="(car, index) in Menuitem"
        :key="index"
        :NameProduct="car.NameProduct"
        :img="car.img"
        :Price="car.Price"
        @Order="menuorder"
      />
    </div>

    <user :Total="Total" :Data="Data" />
    <table class="table">
      <thead class="thead-yyy">
        <tr>
          <th scope="col">Product</th>
          <th scope="col">Price</th>
          <th scope="col">Piece</th>
          <th scope="col">Total</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(da, index) in Data" :key="index">
          <td>{{ da.NameProduct }}</td>
          <td>{{ da.Price }}</td>
          <td>{{ da.Amount }}</td>
          <td>{{ da.Total }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
// @ is an alias to /src
import User from "../components/User.vue";

export default {
  name: "About",
  components: {
    User
  },
  props: {
    Total: Number,
    Data: Array,
    Menuitem: Array
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
.bg-black{
  color: #000;
}

</style>