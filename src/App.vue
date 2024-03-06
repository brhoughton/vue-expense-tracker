<template>
  <Header />
  <div class="container">
    <Balance />
    <IncomeExpenses />
    <TransactionList :transactions="transactions" />
    <AddTransaction />
  </div>
</template>

<script setup>
import Header from "./components/Header.vue";
import Balance from "./components/Balance.vue";
import IncomeExpenses from "./components/IncomeExpenses.vue";
import TransactionList from "./components/TransactionList.vue";
import AddTransaction from "./components/AddTransaction.vue";

import { ref } from 'vue';

const transactions = [
  { id: 1, text: "Raley's", amount: -147.98 },
  { id: 2, text: "Chevron", amount: -98.24 },
  { id: 3, text: "Amazon", amount: -13.98 },
  { id: 4, text: "ACH Deposit", amount: 4166.66 },
  { id: 5, text: "Apple", amount: -9.99 },
];
</script>
