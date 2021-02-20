<template>
  <div class="col-lg-3">
    <b-card
      border-variant="primary"
      :header="NameProduct"
      header-bg-variant="dark"
      header-text-variant="white"
      align="center"
      style="height: 30rem"
      ><b-container>
        <b-card-img
          :src="img"
          alt="Image"
          tag="article"
          style='height: 200px; width: 200px; object-fit: contain'
          class="mb-2"
        ></b-card-img
      ></b-container>
      <b-card-text><h3>Price : {{ Price }} usd</h3></b-card-text>
      <b-form-spinbutton
        id="sb-small"
        size="sm"
        v-model="Amount"
        class="mb-5"
      ></b-form-spinbutton>
      <div>
        <button type="button" class="btn btn-outline-info" @click="Order()">
         Add to cart
      </button>
      </div>
    </b-card>
  </div>
</template>
<script>
export default {
  props: {
    NameProduct: String,
    img: String,
    Price: Number
  },
  data() {
    return {
      Amount: 1
    };
  },
  methods: {
    Order() {
      alert("Please press  Submit to confirm the product you have chosen ");
      this.$emit("Order", {
        NameProduct: this.NameProduct,
        Price: this.Price,
        Amount: this.Amount,
        Total: this.Price * this.Amount
      });
    }
  }
};
</script>
<style>
.btn-outline-info {
    color: #0e530c;
    border-color: #0e530c;
}
.btn-outline-info:hover {
    color: #fff;
    background-color: #0e530c;
    border-color: #17a2b8;
}
</style>
