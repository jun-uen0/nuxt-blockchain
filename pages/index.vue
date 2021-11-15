<template>
	<div>
    <h1>Blockchain, Smartcontract app using Nuxt.js</h1>
		<p>
			<input
			type="text"
			v-model="inputNumber"
			placeholder="input number"
			>
			<button
			@click="setNumber()"
			>
			Set Number to contract
			</button>
		</p>
		<p>
			<button
			@click="getNumber()"
			>
			Get Number from contract
			</button>
			Number : {{number}}
		</p>
	</div>
</template>

<script>
export default {
  data() {
    return {
      number: 0, // retrive from contract
      inputNumber: 0 // input form
    }
  },
  methods: {
    getNumber: async function() {
      let ret = await this.$contract.methods.get().call()
      console.log(ret)
      console.log(this.$web3.eth.getAccounts)
      this.number = ret
    },
    setNumber: async function() {
      let accounts = await this.$web3.eth.getAccounts()
      let account = accounts[0]
      let ret = await this.$contract.methods.set(this.inputNumber).send({from: account})
    },
  },
  mounted() {
    console.log('Current Block Number')
    this.$web3.eth.getBlockNumber().then(console.log)
  }
}
</script>
