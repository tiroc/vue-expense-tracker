<template>
  <Header />
  <div class="container"></div>
    <Balance />
</template>
<script>
  import Header from './components/Header.vue';
  import Balance from './components/Balance.vue';

  export default{
    components:{
      Header,
      Balance,
    },
  };
</script>