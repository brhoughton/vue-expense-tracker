<template>
  <Header />
  <div class="container">
    <Balance :total="total" />
    <IncomeExpenses :income="income" :expenses="expenses" />
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

import { ref, computed } from 'vue';

const transactions = ref([
  { id: 1, text: "Raley's", amount: -147.98 },
  { id: 2, text: "Chevron", amount: -98.24 },
  { id: 3, text: "Amazon", amount: -13.98 },
  { id: 4, text: "ACH Deposit", amount: 4166.00 },
  { id: 5, text: "ATM Deposit", amount: 120.00 },
]);

const total = computed(() => {
  return transactions.value.reduce((acc, transaction) => {
    return acc + transaction.amount;
  }, 0);
});

const income = computed(() => {
  return transactions.value
    .filter((transaction) => transaction.amount > 0)
    .reduce((acc, transaction) => {
      return acc + transaction.amount;
    }, 0)
    .toFixed(2);
});

const expenses = computed(() => {
  return transactions.value
    .filter((transaction) => transaction.amount < 0)
    .reduce((acc, transaction) => {
      return acc + transaction.amount;
    }, 0)
    .toFixed(2);
});
</script>
