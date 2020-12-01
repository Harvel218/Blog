<template>
  <div class="container">
    <nav class="page_title_wraper">
      <p class="hello_message">Go, get anything You dreamed of</p>
    </nav>
    <main>
      <ul>
        <li v-for="article of articles" :key="article.slug">
          <NuxtLink :to="{ name: 'blog-slug', params: { slug: article.slug } }">
            <ArticlePreview
              :title="article.title"
              :author="article.author"
              :date="article.date"
            >
            </ArticlePreview
          ></NuxtLink>
        </li>
      </ul>
    </main>
    <footer></footer>
  </div>
</template>

<script>
import Vue from 'vue'
import ArticlePreviewVue from '~/components/ArticlePreview.vue'

export default Vue.extend({
  async asyncData({ $content, params }) {
    const articles = await $content('articles', params.slug)
      .only(['title', 'date', 'img', 'slug', 'author'])
      .sortBy('post_number', 'asc')
      .fetch()
    return {
      articles,
    }
  },
})

console.log(ArticlePreviewVue)
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
      font-weight: 550;
      padding: 2px 10px;
      text-decoration:underline;
      color:$main_page_color;
    }
  }
  & main {
    width: 100%;
    height: auto;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center;

    & ul {
      display: flex;
      flex-direction: column-reverse;

      & .article_container {
        width: 100%;
        height: auto;
        max-height: 550px;
        margin-bottom: 20px;
      }
    }
  }
}

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
