<template>
  <div class="container">
    <nav class="page_title_wraper">
      <p class="hello_message">Go, get anything You dreamed of</p>
    </nav>
    <main>
      <ArticlePreview /><ArticlePreview /><ArticlePreview /><ArticlePreview /><ArticlePreview />
    </main>
    <footer></footer>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({})
</script>

<style lang="scss">
.container {
  margin: 0 auto;
  padding: 0 20px;
  min-height: 100vh;
  width: 100%;
  text-align: center;
  & .page_title_wraper {
    width: 100%;
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    height: 40px;
    margin: 30px 0;

    & .hello_message {
      font-size: 16.5px;
      color: black;
      font-weight: 550;
      padding: 2px 10px;
      border-bottom: 2px solid black;
    }
  }
  & main {
    width: 100%;
    min-height: 40vh;
    height: auto;
    background-color: #c0c0c0;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: space-between;

    & section {
      min-width: 300px;
      width: 40%;
      background-color: darkred;
      margin-bottom: 15px;
    }
  }
}
// .title {
//   font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
//     'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
//   display: block;
//   font-weight: 300;
//   font-size: 100px;
//   color: #35495e;
//   letter-spacing: 1px;
// }
.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}
.links {
  padding-top: 15px;
}
</style>
