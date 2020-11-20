<template>
  <section class="article_container">
    <p class="article_title">something</p>
    <p class="brief_description">something</p>
  </section>
</template>

<style lang="scss">
.article_container {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-start;

  & p {
    padding-left: 10px;
    padding-right:10px;

    &.article_title {
      font-size: 17.5px;
      margin-bottom: 5px;
      padding-bottom:2px;
      padding-top: 8px;
      border-bottom: 2px solid black;
    }

    &.brief_description{
      font-size: 16.5px;
      padding-top:5px;
      padding-bottom:10px;
    }
  }
}
</style>
