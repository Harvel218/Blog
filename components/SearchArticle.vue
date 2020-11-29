<template>
  <article class="search_area">
    <input
      v-model="searchQuery"
      type="search"
      autocomplete="off"
      placeholder="Search for anything.."
    />

    <nav class="search_resoult">
      <ul v-if="articles.length">
        <li v-for="article of articles" :key="article.slug">
          <NuxtLink :to="{ name: 'blog-slug', params: { slug: article.slug } }">
            {{ article.date }} - <i>{{ article.author }}</i> :<br />
            - <b>{{ article.title }}</b>
          </NuxtLink>
        </li>
      </ul>
    </nav>
  </article>
</template>

        <script>
export default {
  data() {
    return {
      searchQuery: '',
      articles: [],
    }
  },
  watch: {
    async searchQuery(searchQuery) {
      if (!searchQuery) {
        this.articles = []
        return
      }
      this.articles = await this.$content('articles')
        .limit(6)
        .search(searchQuery)
        .fetch()
    },
  },
}
</script>
        <style lang="scss">
.search_area {
  display: flex;
  flex-wrap: nowrap;
  justify-content: flex-end;
  align-items: center;
  width: calc(100% - 135px);
  max-width: 500px;
  margin-right: 15px;

  & input {
    border-radius: 5px 0 0 5px;
    outline: none;
    border: 2px solid $main_page_color;
    background-color: #fff;
    min-width: 150px;
    width: calc(100% - 30px);
    max-width: 475px;
    height: 39px;
    font-size: 16.5px;
    color: $main_page_color;
    padding-left: 10px;
    min-height: 0;

    &::placeholder {
      color: #dedede;
    }
  }

  & .search_resoult {
    width: auto;
    min-width: 280px;
    max-width: 500px;
    position: absolute;
    top: 74px;
    right: -2px;
    padding-top: 10px;
    padding-bottom: 10px;
    padding-left: 10px;
    padding-right: 0;
    border-radius: 5px;

    @media (max-width: 640px) {
      max-width: unset;
    }
    & ul {
      background-color: $main_page_color;
      width: 100%;
      border-right: 1px solid $main_page_color;
      border-radius: 0 0 5px 5px;
      transition: .5s ease-in-out;

      & li {
        display: block;
        background-color:$bright_color;

        & a {
          display: block;
          padding: 10px 10px 10px 10px;
          width: 100%;
          height: 100%;
                transition: .3s;

          &:hover {
            background-color: $main_page_color;
          }
        }
      }
    }
  }
}
</style>
