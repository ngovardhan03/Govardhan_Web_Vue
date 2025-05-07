
<template>
  <footer>
    <h1> {{ storeinfo }} </h1>
  </footer>
</template>

<script>
export default {
  props: {
    storeinfo: {
      type: Number,
      required: true,
    },
  },
};
</script>

<style scoped>

footer {
  background-color: #1a237e;
  padding: 10px;
  text-align: center;
}
footer h1{
  color:aliceblue
}
</style>


