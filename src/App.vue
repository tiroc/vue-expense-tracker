<template>
  <Header />
  <div class="container"></div>
    <Balance :total="total"/>
    <IncomeExpenses :income="income" :expenses="expenses" />
    <TransactionList :transactions="transactions"/>
    <AddTransaction />
</template>
<script setup>
  import Header from './components/Header.vue';
  import Balance from './components/Balance.vue';
  import IncomeExpenses from './components/IncomeExpenses.vue';
  import TransactionList from './components/TransactionList.vue';
  import AddTransaction from './components/AddTransaction.vue';

  import   { ref, computed } from 'vue';

  const transactions = ref([
    {id: 1, text: 'Flower', amount: -20},
    {id: 2, text: 'Takeout', amount: -99},
    {id: 3, text: 'Old PC', amount: +900},
  ]);
  const total = computed(()=>{
    return transactions.value.reduce((acc, transaction)=>{
      return acc + transaction.amount;
    }, 0);
  });

  const income = computed(()=>{
    return transactions.value
      .filter((transaction)=>transaction.amount > 0)
      .reduce((acc, transaction)=>{
        return acc + transaction.amount;
      }, 0)
      .toFixed(2);
  });

  const expenses = computed(()=>{
    return transactions.value
      .filter((transaction)=>transaction.amount < 0)
      .reduce((acc, transaction)=>{
        return acc + transaction.amount;
      }, 0)
      .toFixed(2);
  });
</script>