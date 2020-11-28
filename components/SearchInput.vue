<template>
  <form class="search_box">
    <input
      v-model="searchQuery"
      type="search"
      autocomplete="off"
      placeholder="Search for anything.."
    />
    <ul v-if="articles.length">
      <li v-for="article of articles" :key="article.slug">
        <NuxtLink :to="{ name: 'blog-slug', params: { slug: article.slug } }">
          {{ article.title }}{{article.date}}
        </NuxtLink>
      </li>
    </ul>
  </form>
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
.search_box {
  display: flex;
  flex-wrap: nowrap;
  justify-content: flex-end;
  align-items: center;
  width: calc(100% - 135px);
  max-width: 500px;
  margin-right: 20px;

  & input {
    border-radius: 5px;
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

    &::placeholder {
      color: #dedede;
    }
  }
}
</style>
