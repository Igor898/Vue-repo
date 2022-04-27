<template>
    <div>
        <button class="showPaymentForm" @click="show=!show">ADD NEW COST +</button>
        <div class="paymentForm" v-show="show">
            <input v-model="date" placeholder="Date">
            <input v-model="category" placeholder="Category">
            <input v-model="value" placeholder="Value">
            <br>
            <button @click="AddClicker">+ Add</button>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            show: false,
            date: '',
            category: '',
            value: ''
        }
    },
    methods: {
        AddClicker() {
            const data = {
                date: this.date,
                category: this.category,
                value: this.value
            }
            this.$emit('addPayment', data)
        }
    },
}
</script>