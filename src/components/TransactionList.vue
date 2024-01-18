<template>
    <h3>History</h3>
    <ul id="list" class="list">
        
        <li v-for="transaction in transactions" v-bind:key="transaction.id" :class="transaction.amount < 0 ? 'minus' : 'plus'">
            {{ transaction.text }}
            <span>R{{ transaction.amount }}</span>
            <button class="delete-btn">x</button>
        </li>
    </ul>
</template>

<script>
    export default{
        data(){
            return {
                transactions: [
                    {id: 1, text: 'Flower', amount: -20},
                    {id: 2, text: 'Takeout', amount: -99},
                    {id: 3, text: 'Old PC', amount: +900},
                ],
            };
        }
    }
</script>