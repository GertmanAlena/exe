<template>
  <div>
    <input type="text" id="loanAmount" v-model="loanAmount" required>
    <input type="text" id="interestRate" v-model="interestRate" required>
    <input type="text" id="loanTerm" v-model="loanTerm" required>
    <p>Monthly Payment: {{ monthlyPayment }}</p> 
    <p>Total Interest: {{ totalPayment }}</p>
  </div>
</template>

<script>
export default {
    name: 'MortgageCalculator',
    data() {
        return {
            loanAmount: 0,
            interestRate: 0,
            loanTerm: 0,
        };
    },
    methods: {},
    computed: {
        monthlyPayment() {
            const rate = this.interestRate / 100 / 12;
            const term = this.loanTerm;
            const principal = this.loanAmount;
            const numerator = rate * Math.pow(1 + rate, term);
            const denominator = Math.pow(1 + rate, term) - 1;
            const payment = principal * (numerator / denominator);
            return payment.toFixed(2);
        },
        totalPayment() {
            const term = this.loanTerm;
            const payment = parseFloat(this.monthlyPayment);
            return term * payment;
        },
    }
}
</script>