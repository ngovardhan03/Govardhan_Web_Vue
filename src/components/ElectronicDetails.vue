<template>
  <div class="flex-container">
    <div v-for="item in branddetails" :key="item.id" class="container">
      <h2> Company: {{ item.BrandName }} <hr></h2>
      <p>Model:{{ item.ProductName }}</p>
      <p>Price: {{ item.Price }}</p>
      <p>Specifications: {{ item.Specification }}</p>
      <p>Return Policy: {{ item.ReturnPolicy }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ElectronicDetails',
  props: {
    branddetails: Array,
  },
};
</script>

<style scoped>
.flex-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
  margin: 10px;
}

.container {
  display: grid;
  grid-template-rows: repeat(5, 1fr);
  width: 90%;
  padding: 5px;
  background-color: #e6d9d9;  
}
</style>