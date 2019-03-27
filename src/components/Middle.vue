<template>
  <article>
    <div class="wrapper">
      <div class="content">
        <div class="ant">
          <span>LAST BLOCK</span>
          <span>{{ lastBlock }}</span>
        </div>
        <div class="ant">
          <span>TRANSACTIONS</span>
          <span>{{ transactions }}</span>
        </div>
        <div class="ant">
          <span>ACCOUNTS</span>
          <span>{{ accounts }}</span>
        </div>
        <div class="ant">
          <span>CURRENT TPS</span>
          <span>{{ currentTps }}</span>
        </div>
        <div class="ant">
          <span>HIGHEST</span>
          <span>{{ highest }}</span>
        </div>
        <div class="ant">
          <span>DAPPS</span>
          <span>{{ dApps }}</span>
        </div>
      </div>
    </div>
  </article>
</template>

<script>
import axios from 'axios'
export default {
  name: 'Middle',
  data () {
    return {
      lastBlock: 0,
      transactions: 0,
      accounts: 0,
      currentTps: 0,
      highest: 0,
      dApps: 0,
      time: ''
    }
  },
  methods: {
    aysncData: function () {
      axios.get('http://47.99.236.226:8060/query/block/getMobileData').then((res) => {
        this.lastBlock = res.data.data.lastBlock
        this.transactions = res.data.data.transactions
        this.accounts = res.data.data.accounts
        this.currentTps = res.data.data.currentTps
        this.highest = res.data.data.highest
        this.dApps = res.data.data.price
      })
    }
  },
  created () {
    this.aysncData()
  },
  mounted () {
    this.time = setInterval(() => {
      this.aysncData()
    }, 1800)
  }

}
</script>

<style scoped>
  span{
    display: block;
  }

  article {
    background: url("../assets/mb-bg.png") no-repeat fixed center;
    width: 100%;
    height: 6rem;
    background-size: cover;
  }

  .wrapper {
    width: 100%;
    margin: 0 auto;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
  }

  .content {
    width: 100%;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    flex-direction: row;
    flex-wrap: wrap;
  }

  .ant {
    width: 3rem;
    height: 1.2rem;
    display: block;
    border-radius: 0.1rem;
    margin: 0.3rem;
    color: white;
    text-align: center;
  }

  .ant span{
    font-size: 0.2rem;
  }

  .ant span:nth-child(1){
    margin-top: 0.2rem;
  }

  .ant span:nth-child(2){
    margin-top: 0.1rem;
  }

  .ant:nth-child(1) {
    background: linear-gradient(to top, #04aea1, #11e4f8);
    margin-left: 1rem;
  }

  .ant:nth-child(2) {
    background: linear-gradient(to top, #46d7ff, #46d7ff);
    margin-right: 1rem;
  }

  .ant:nth-child(3) {
    background: linear-gradient(to top, #54a348, #ace573);
    margin-left: 1rem;
  }

  .ant:nth-child(4) {
    background: linear-gradient(to top, #d13592, #f872c0);
    margin-right: 1rem;
  }

  .ant:nth-child(5) {
    background: linear-gradient(to top, #d15735, #f87272);
    margin-left: 1rem;
  }

  .ant:nth-child(6) {
    background: linear-gradient(to top, #ca8303, #fec763);
    margin-right: 1rem;
  }
</style>
