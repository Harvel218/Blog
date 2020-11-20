<template>
  <section class="article_container">
    <p class="article_title">something</p>
    <p class="brief_description">Lorem ipsum dolor sit amet
      Lorem ipsum dolor sit amet
      Lorem ipsum dolor sit amet
      Lorem ipsum dolor sit amet
      Lorem ipsum dolor sit amet
      Lorem ipsum dolor sit amet
      Lorem ipsum dolor sit amet
      Lorem ipsum dolor sit amet
      Lorem ipsum dolor sit amet
      Lorem ipsum dolor sit amet
      Lorem ipsum dolor sit amet
      Lorem ipsum dolor sit amet
      Lorem ipsum dolor sit amet
      Lorem ipsum dolor sit amet
      Lorem ipsum dolor sit amet
      Lorem ipsum dolor sit ametLorem ipsum dolor sit amet
      Lorem ipsum dolor sit amet
      Lorem ipsum dolor sit amet
    </p>

    <article class="tags">
      <nav>
        <p class="tag">#Książki</p>
        <p class="tag">#PolishWoman</p>
        <p class="tag">#WhiteAfrican</p>
        <p class="tag">#GayFemale</p>
        <p class="tag">#GayFemale</p>
      </nav>
    </article>
  </section>
</template>

<style lang="scss">
.article_container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-start;
  position: relative;

  & p {
    padding-left: 15px;
    padding-right: 15px;

    &.article_title {
      font-size: 16.5px;
      margin-bottom: 5px;
      padding-bottom: 2px;
      padding-top: 15px;
      border-bottom: 2px solid black;
    }

    &.brief_description {
      font-size: 14.5px;
      padding-top: 5px;
      padding-bottom: 10px;
      width:100%;
      height:250px;
      text-align:left;
      overflow: hidden;
    }
  }

  & .tags {
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
    width: 100%;

    & nav {
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      justify-content: space-around;
      width: 100%;
      padding: 10px;
      font-size: 13px;

      & .tag {
        padding: 0 5px;
      }
    }
  }
}
</style>
