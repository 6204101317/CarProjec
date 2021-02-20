<template>
  <div id="app">
   <navbar></navbar>
  </div>
</template>
<script>
import navbar from './components/navbar.vue';
export default {
  components: { navbar },
 
};
</script>

<style>
#nav a.router-link-exact-active {
  color: #fdfafa;
}
.bg-info {
  background-color: #0d4736 !important;
}
#nav a {
  font-weight: bold;
  color: #e6e7e9;
}

</style>
