<template>
  <div>
    <h2>Карта товаров</h2>
        <div>
            <form>
                <div>
                    <input type="text" id="price1" v-model="quantity1" required>
                    <p>Price: {{ price1 }}</p>
                    <p>Subtotal: {{ subtotal1 = sum(quantity1, price1) }} </p>
                </div>
                <div>
                    <input type="text" id="price2" v-model="quantity2" required>
                    <p>Price: {{ price2 }}</p>
                    <p>Subtotal: {{ subtotal2 = sum(quantity2, price2) }} </p>
                    <p>Total: {{ sumTotal(subtotal1, subtotal2) }}</p>
                </div>
            </form>
        </div>
  </div>
</template>

<script>
export default {
  name: 'CardComponent',

  data() {
    return {
        price1: 10,
        quantity1: 0,
        price2: 10,
        quantity2: 0,
        total: 0,
        subtotal1: 0,
        subtotal2: 0
    };
  },

  mounted() {
    
  },

  methods: {
    sumTotal(){
        return Number(this.subtotal1) + Number(this.subtotal2)
    },
    sum(quantity, price){
        return Number(quantity) * Number(price)
    },
    
  },
};
</script>