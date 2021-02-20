<template>
  <div>
    <div class="card bg-1 mb-3" style="max-width: 120rem">
      <div class="card-body">
        <div class="row justify-content-end">
          <h1 class="col-lg-4">Total : {{ Total }} usd</h1>
          <button type="button " class="btn btn-success mr-4" @click="sum()">
            <h1>BUY</h1>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    Total: Number,
    Data: Array
  },
  data() {
    return {
      Name: "",
      Tel: ""
    };
  },
  methods: {}
};
</script>

<style scoped>
.bg-1 {
  background-color: rgb(85, 85, 85);
  color: rgb(255, 255, 255);
}
</style>
