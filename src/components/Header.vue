<template>
  <header>
    <div class="wrapper">
      <div class="content-left">
        <img src="../assets/logo.svg">
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'header'
}
</script>

<style scoped>
  header {
    width: 100%;
    background: rebeccapurple;
    height: 1rem;
  }

  img {
    margin-top: 0.2rem;
    margin-left: 0.2rem;
    width: 2rem;
    height: 0.5rem;
  }

  .wrapper {
    width: 100%;
    margin: 0 auto;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
  }
  .content-left{
    display: flex;
  }
</style>
