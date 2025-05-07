<template>
  <div id="app">
    <my-header :Name="Title" />
    <electronic-details :branddetails="ProductDetails" />
    <my-footer :storeinfo="Info" />
    <div v-if="loading">Data Loading...</div>
    
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue';
import ElectronicDetails from './components/ElectronicDetails.vue';
import MyFooter from './components/MyFooter.vue';

export default {
  name: 'App',
  components: {
    MyHeader,
    ElectronicDetails,
    MyFooter,
  },
  data() {
    return {
      Title: 'Electronics Gallery',
      ProductDetails: [],
    Info: 'For More info visit our store',
      loading: true,
      error: null,
    };
  },
  methods: {
    async fetchdetails() {
      try {
        const response = await fetch('https://govardhan-web-node.onrender.com/api');
        if (!response.ok) {
          throw new Error('Network response was not ok');
        }
        const data = await response.json();
        this.ProductDetails = data;
        console.log('Data fetched:', data);
      } catch (error) {
        console.error('Error fetching news feed:', error.message);
        this.error = 'Error fetching data. Please try again later.';
      } finally {
        this.loading = false;
      }
    },
  },
  async created() {
    await this.fetchdetails();
  },
};
</script>

<style>
body {
  font-family: 'Montserrat', sans-serif;
  margin: 0;
  padding: 0;
}

#app {
  text-align: center;
  margin-top: 20px;
}

#app div {
  margin-top: 10px;
  font-weight: bold;
  color: black;
}


</style>