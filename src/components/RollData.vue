<template>
  <article>
    <div class="wrapper">
      <div class="content-top">
        <div class="content-top-header">
          <div class="content-top-header-left">
            <img src="../assets/block.png">
            <span>BLOCKS</span>
          </div>
        </div>
        <div class="content-top-content">
          <p>
              <span>
                  Block Hash {{ block[0].hash }}
              </span>
          </p>
          <p>
              <span>
                  Transactions {{ block[0].transactions[0].number }}
              </span>
          </p>
          <p>
              <span>
                  Proposer {{ block[0].proposal }}
              </span>
          </p>
        </div>
        <div class="content-top-content">
          <p>
              <span>
                  Block Hash {{ block[1].hash }}
              </span>
          </p>
          <p>
              <span>
                  Transactions {{ block[1].transactions[0].number }}
              </span>
          </p>
          <p>
              <span>
                  Proposer {{ block[1].proposal }}
              </span>
          </p>
        </div>
        <div class="content-top-content">
          <p>
              <span>
                  Block Hash {{ block[2].hash }}
              </span>
          </p>
          <p>
              <span>
                  Transactions {{ block[2].transactions[0].number }}
              </span>
          </p>
          <p>
              <span>
                  Proposer {{ block[2].proposal }}
              </span>
          </p>
        </div>
        <div class="content-top-content">
          <p>
              <span>
                  Block Hash {{ block[3].hash }}
              </span>
          </p>
          <p>
              <span>
                  Transactions {{ block[3].transactions[0].number }}
              </span>
          </p>
          <p>
              <span>
                  Proposer {{ block[3].proposal }}
              </span>
          </p>
        </div>
      </div>
      <div class="content-bottom">
        <div class="content-bottom-header">
          <div class="content-bottom-header-left">
            <img src="../assets/block.png">
            <span>TRANSACTIONS</span>
          </div>
        </div>
        <div class="content-bottom-content">
          <p>
              <span>
                  Block Hash {{ block[0].hash }}
              </span>
          </p>
          <p>
              <span>
                  Transactions {{ block[0].transactions[0].number }}
              </span>
          </p>
          <p>
              <span>
                  Proposer {{ block[0].proposal }}
              </span>
          </p>
        </div>
      </div>
      <div class="content-bottom-content">
        <p>
              <span>
                  Block Hash {{ block[0].hash }}
              </span>
        </p>
        <p>
              <span>
                  Transactions {{ block[0].transactions[0].number }}
              </span>
        </p>
        <p>
              <span>
                  Proposer {{ block[0].proposal }}
              </span>
        </p>
      </div>
      <div class="content-bottom-content">
        <p>
              <span>
                  Block Hash {{ block[1].hash }}
              </span>
        </p>
        <p>
              <span>
                  Transactions {{ block[1].transactions[0].number }}
              </span>
        </p>
        <p>
              <span>
                  Proposer {{ block[1].proposal }}
              </span>
        </p>
      </div>
      <div class="content-bottom-content">
        <p>
              <span>
                  Block Hash {{ block[2].hash }}
              </span>
        </p>
        <p>
              <span>
                  Transactions {{ block[2].transactions[0].number }}
              </span>
        </p>
        <p>
              <span>
                  Proposer {{ block[2].proposal }}
              </span>
        </p>
      </div>
      <div class="content-bottom-content">
        <p>
              <span>
                  Block Hash {{ block[3].hash }}
              </span>
        </p>
        <p>
              <span>
                  Transactions {{ block[3].transactions[0].number }}
              </span>
        </p>
        <p>
              <span>
                  Proposer {{ block[3].proposal }}
              </span>
        </p>
      </div>
    </div>
  </article>
</template>

<script>
import axios from 'axios'

export default {
  name: 'RollData',
  data () {
    return {
      block: []
    }
  },
  methods: {
    aysncData: function () {
      axios.get('http://47.99.236.226:8060/query/block/getMobileData').then((res) => {
        console.log(res.data.data.blockData)
        this.block = res.data.data.blockData
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
  article {
    width: 100%;
    margin-bottom: 1rem;
  }

  .wrapper {
    width: 95%;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }

  .content-top {
    margin-top: 0.6rem;
  }

  .content-top-header {
    display: flex;
    background: gray;
    justify-content: left;
    height: 1rem;
  }

  .content-top-header-left {
    display: flex;
  }

  .content-top-header-left img {
    width: 0.3rem;
    height: 0.3rem;
    margin-top: 0.3rem;
    margin-left: 0.5rem;
  }

  .content-top-header-left span {
    color: white;
    font-size: 0.3rem;
    margin-top: 0.3rem;
    margin-left: 0.3rem;
  }

  .content-top-content {
    display: flex;
    flex-direction: column;
  }

  .content-top-content p {
    width: 100%;
    margin-top: 0.3rem;
  }

  .content-top-content p span {
    width: 9rem;
    display: block;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
    color: gray;
    font-size: 0.1rem;
  }

  .content-bottom-header {
    display: flex;
    background: gray;
    justify-content: left;
    height: 1rem;
    margin-top: 1rem;
  }

  .content-bottom-header-left {
    display: flex;
  }

  .content-bottom-header-left img {
    width: 0.3rem;
    height: 0.3rem;
    margin-top: 0.3rem;
    margin-left: 0.5rem;
  }

  .content-bottom-header-left span {
    color: white;
    font-size: 0.3rem;
    margin-top: 0.3rem;
    margin-left: 0.3rem;
  }

  .content-bottom-content {
    display: flex;
    flex-direction: column;
  }

  .content-bottom-content p {
    width: 100%;
    margin-top: 0.3rem;
  }

  .content-bottom-content p span {
    width: 9rem;
    display: block;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
    color: gray;
    font-size: 0.1rem;
  }

</style>
