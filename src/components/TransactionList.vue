<template>
  <h3>History</h3>
  <ul id="list" class="list">
    <li v-for="transaction in transactions" :key="transaction.id">
      Cash <span>-$400</span><button class="delete-btn">x</button>
    </li>
  </ul>
</template>

<script>
  export default {
    data() {
      return {
        transactions: [
          { id: 1, text: "Raleys", amount: -147.98 },
          { id: 2, text: "Chevron", amount: -98.24 },
          { id: 3, text: "Amazon", amount: -13.98 },
          { id: 4, text: "Apple", amount: -9.99 },
        ],
      };
    },
  };
</script>
