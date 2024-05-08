<template>
  <div class="product-container">
    <div class="product" v-for="(product, index) in products" :key="index">
      <p>Name: {{ product.name }}</p>
      <p>Price: {{ formattedPrice(product.price) }}</p>
      <div class="status">
        <p>Status:</p>
        <p class="status-text">{{ productStatus(product.status) }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeWork',

  data() {
    return {
      name: '',
      price: 0,
      status: false,
      products: [
        {
          name: 'Apple',
          price: 100,
          status: true
        },
        {
          name: 'Orange',
          price: 200,
          status: false
        },
        {
          name: 'Banana',
          price: 300,
          status: true
        }
      ]
    };
  },

  mounted() {
    
  },

  methods: {
    productStatus(status){
        if (status == true) {
            return 'Available'
        } 
        else {
            return 'Out of stock'
        }
    },
    formattedPrice(price) {
        return `"$${price}"`;
    }
  },
};
</script>
<style scoped>
    .product-container {
        display: flex;
        gap: 30px;
    }
    .product {
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 140px;	
        background: rgb(249, 243, 215);
        outline: 2px solid #000;
        border: 3px solid #fff;
        border-radius: 10px; 
    }
    .status-text {
        color: green;
    }
</style>
