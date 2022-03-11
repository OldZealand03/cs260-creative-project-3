<template>
  <div class="about">
    <h1>This is a browse page</h1>
    
  </div>
</template>

<script>
export default {
  name: "BrowseStuff",
//   props: {
//     products: Array,
//   },
  methods: {
    deleteFromCart(product) {
      const index = this.$root.$data.cart.indexOf(product);
      if (index > -1) {
        this.$root.$data.cart.splice(index, 1);
      }
    },
  },
  computed: {
    cartTotal() {
      let total = 0;
      for (let i = 0; i < this.$root.$data.cart.length; ++i) {
        console.log("." + this.$root.$data.cart[i].price);
        let amount = this.$root.$data.cart[i].price
        total += parseFloat(amount.replace('$', ''));
      }
      return total.toFixed(2);
    },
  },
};
</script>