<template>
  <Header />
  <div class="container"></div>
    <Balance />
    <IncomeExpenses />
</template>
<script>
  import Header from './components/Header.vue';
  import Balance from './components/Balance.vue';
  import IncomeExpenses from './components/IncomeExpenses.vue';

  export default{
    components:{
      Header,
      Balance,
      IncomeExpenses,
    },
  };
</script>