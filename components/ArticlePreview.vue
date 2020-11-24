<template>
  <section class="article_container">
    <nav class="article_info">
      <span class="date">22.08.2020</span>
      <span
        ><span class="author">Krzysztof Gacek</span>
        <span class="tag">#angular</span></span
      >
    </nav>
    <header class="article_title">Co sądze o TypeScript na poważnie?</header>
    <aside class="article_img"><img src="" alt="" /></aside>
  </section>
</template>

<style lang="scss">
.article_container {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: flex-start;
  position: relative;
  padding: 5px;
  border-bottom: 2px solid #f2f4f5;
  transition: 0.3s ease-in-out;
  cursor: pointer;
  margin-bottom: 40px;
  flex-wrap: wrap;

  &:hover {
    background-color: #f2f4f5;
    opacity: 80%;
  }

  &:active {
    transform: scale(0.95);
  }

  & .article_info {
    // top: -18px;
    // left: 5px;
    font-size: 12.5px;
    display: flex;
    justify-content: space-between;
    width: 100%;
    padding-bottom:5px;

    & .author {
      padding-right: 15px;
    }
  }

  & .article_title {
    font-size: 16.5px;
    margin-bottom: 5px;
    width: calc(100% - 30px);
    text-align: left;
    padding-right: 10px;
  }

  & .article_img {
    width: 30px;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: lightcyan;

    & img {
      width: 30px;
      height: 30px;
    }
  }
}
</style>
