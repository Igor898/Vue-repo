<template>
  <div class="hello">
    <header>
      <h1>{{ msg }}</h1>
    </header>
    <main>
      <payments-display :items="paymentsList"/>
      <add-payment-form @addPayment="AddPaymentData"/>
    </main>
  </div>
</template>

<script>
import AddPaymentForm from './AddPaymentForm.vue'
import PaymentsDisplay from './PaymentsDisplay.vue'

export default {
  components: { PaymentsDisplay, AddPaymentForm },
  name: 'HelloWorld',
  props: {
    msg: String
  }, 
  data() {
    return {
      paymentsList: []
    }
  },
  methods: {
    AddPaymentData(data) {
      this.paymentsList.push(data)
    },
    fetchData() {
      return [
        {
          date: '28.03.2020',
          category: 'Food',
          value: 169,
        },
        {
          date: '24.03.2020',
          category: 'Transport',
          value: 360,
        },
        {
          date: '24.03.2020',
          category: 'Food',
          value: 532,
        },
      ]     
    }
  },
  created() {
    this.paymentsList = this.fetchData()
  },
}
</script>

<style scoped>

</style>
