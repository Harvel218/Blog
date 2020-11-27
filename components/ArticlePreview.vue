<template>
  <section class="article_container">
    <nav class="article_info">
      <span class="date">{{ date }}</span>
      <span class="info"
        ><span class="author">{{ author }}</span>
        <span class="tag">{{ tag }}</span></span
      >
    </nav>
    <header class="article_title">{{ title }}</header>
    <aside class="article_img"><img src="" alt="" /></aside>
  </section>
</template>

<script>
export default {
  props: ['date', 'author', 'tag', 'title'],
  data: {
    date: '',
    author: '',
    tag: '',
    title: '',
  },
}
</script>

<style lang="scss">
.article_container {
  display: flex;
  flex-direction: row;
  align-items: center;
  border: 2px solid $main_page_color;
  transition: 0.3s ease-in-out;
  cursor: pointer;
  flex-wrap: wrap;

  &:hover {
    background-color: $main_page_color;
    border-radius: 5px;
  }

  &:active {
    transform: scale(0.95);
    border-radius: 5px;
  }

  & .article_info {
    font-size: 12.5px;
    display: flex;
    justify-content: space-between;
    width: 100%;
    padding-bottom: 5px;

    & .date {
      padding: 5px;
      background-color: $main_page_color;
      border-radius: 0 0 5px 0;

      &.author {
        padding-right: 15px;
      }
    }

    & .info {
      padding: 5px;
      background-color: $main_page_color;
      border-radius: 0 0 0 5px;
    }
  }

  & .article_title {
    font-size: 16.5px;
    margin-bottom: 5px;
    width: calc(100% - 40px);
    text-align: left;
    padding: 0 5px;
    font-weight: 550;
  }

  & .article_img {
    width: 30px;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: $main_page_color;
    padding: 0 5px;
    margin-bottom: 5px;

    & img {
      width: 30px;
      height: 30px;
    }
  }
}
</style>
