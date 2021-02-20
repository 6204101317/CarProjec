<template>
  <div class="home">
    <div class="row">
      <product 
        v-for="(item, index) in Menuitem"
        :key="index"
        :NameProduct="item.NameProduct"
        :img="item.img"
        :Price="item.Price"
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
        <tr v-for="(mi, index) in Data" :key="index">
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
// @ is an alias to /src
import User from "../components/User.vue";

export default {
  name: "Home",
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