<template>
<div>
  <Header class="shadow" />
  <div class="relative flex items-top justify-center min-h-screen bg-gray-100 sm:items-center sm:pt-0">
    <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.1.2/dist/tailwind.min.css" rel="stylesheet">
    <div class="max-w-4xl mx-auto sm:px-6 lg:px-8">
      <h2 class="text-3xl leading-7 font-semibold">
        スマートコントラクト
      </h2>
      <div class="mt-8 bg-white overflow-hidden shadow sm:rounded-lg p-6">
        <p class="mt-3 text-gray-600">
          イーサリアムブロックチェーン上(テストネット)で機能するスマートコントラクトを作成しました。<br/>
          ※ブラウザにMetaMaskが必要です。
          「Set Number to contract」(契約書に数字を入力) に好きな数字を入力してください。数字の大きさはなんでも構いません。仮想通貨の残高とは関係がありません。ただ、「数字」の情報をブロックチェーン上に記載するだけです。
        </p>
        <p>
          <input
          type="text"
          v-model="inputNumber"
          placeholder="input number"
          class="mt-6 text-right"
          >
          <button
          @click="setNumber()"
          class="btn mt-6 bg-gray-100 text-sm p-1 rounded border"
          >
          Set Number to contract
          </button>
        </p>
        <p class="mt-4 pt-4 text-gray-800 border-t border-dashed">
        <p class="mt-3 text-gray-600">
          マイニングされ、ブロックチェーンへ記載されるまでお待ちください。しばらくすると反映されます。
          「Get Number from contract」(契約書から数字を受け取る)をクリックしてください。
          先ほど設定した数字を確認できます。
        </p>
        <p>
          <button
          @click="getNumber()"
          class="btn mt-6 bg-gray-100 text-sm p-1 rounded border"
          >
          Get Number from contract
          </button>
          Number:{{number}}
        </p>
        <p class="mt-4 pt-4 text-gray-800 border-t border-dashed">
          今回は数字で行いましたが、これが例えば「文字」であっても同様なことが可能です。
          これだけの機能だと、既存のWeb技術で可能です。ただ、ブロックチェーンの使用は全ての人が可能で、誰も管理する必要がないのに対して、既存のシステムでは必ず企業や個人なりの管理者が必要となります。さらに、その管理者が万が一データの改竄や削除を行なっても、ほとんどの人は知るすべがありません。<br/>
          昨今巨大IT企業のデータ独占が問題に叫ばれていますが、ブロックチェーン技術を活用すればデータを参加者全員で管理・所有することができます。全員が管理者・監視者となることでデータの改竄・削除を防ぎます。
        </p>
      </div>
      <div class="flex justify-center pt-4 space-x-2">
        <a href="https://github.com/jun-uen0" target="_blank"><svg
          class="w-6 h-6 text-gray-600 hover:text-gray-800"
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          aria-hidden="true"
          role="img"
          width="32"
          height="32"
          preserveAspectRatio="xMidYMid meet"
          viewBox="0 0 24 24"
        ><path d="M12 2.247a10 10 0 0 0-3.162 19.487c.5.088.687-.212.687-.475c0-.237-.012-1.025-.012-1.862c-2.513.462-3.163-.613-3.363-1.175a3.636 3.636 0 0 0-1.025-1.413c-.35-.187-.85-.65-.013-.662a2.001 2.001 0 0 1 1.538 1.025a2.137 2.137 0 0 0 2.912.825a2.104 2.104 0 0 1 .638-1.338c-2.225-.25-4.55-1.112-4.55-4.937a3.892 3.892 0 0 1 1.025-2.688a3.594 3.594 0 0 1 .1-2.65s.837-.262 2.75 1.025a9.427 9.427 0 0 1 5 0c1.912-1.3 2.75-1.025 2.75-1.025a3.593 3.593 0 0 1 .1 2.65a3.869 3.869 0 0 1 1.025 2.688c0 3.837-2.338 4.687-4.563 4.937a2.368 2.368 0 0 1 .675 1.85c0 1.338-.012 2.413-.012 2.75c0 .263.187.575.687.475A10.005 10.005 0 0 0 12 2.247z" fill="currentColor" /></svg></a>
        <a href="https://twitter.com/jun___dev" target="_blank"><svg
          class="w-6 h-6 text-gray-600 hover:text-gray-800"
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          aria-hidden="true"
          role="img"
          width="32"
          height="32"
          preserveAspectRatio="xMidYMid meet"
          viewBox="0 0 24 24"
        ><path d="M22.46 6c-.77.35-1.6.58-2.46.69c.88-.53 1.56-1.37 1.88-2.38c-.83.5-1.75.85-2.72 1.05C18.37 4.5 17.26 4 16 4c-2.35 0-4.27 1.92-4.27 4.29c0 .34.04.67.11.98C8.28 9.09 5.11 7.38 3 4.79c-.37.63-.58 1.37-.58 2.15c0 1.49.75 2.81 1.91 3.56c-.71 0-1.37-.2-1.95-.5v.03c0 2.08 1.48 3.82 3.44 4.21a4.22 4.22 0 0 1-1.93.07a4.28 4.28 0 0 0 4 2.98a8.521 8.521 0 0 1-5.33 1.84c-.34 0-.68-.02-1.02-.06C3.44 20.29 5.7 21 8.12 21C16 21 20.33 14.46 20.33 8.79c0-.19 0-.37-.01-.56c.84-.6 1.56-1.36 2.14-2.23z" fill="currentColor" /></svg></a>
      </div>
    </div>
  </div>
</div>
</template>


<script>
export default {
  data() {
    return {
      number: 0,
      inputNumber: 0
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
