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