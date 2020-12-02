<template>
  <article id="active_article">
    <!-- <pre> {{ article }} </pre> -->
    <nuxt-content :document="article" />
  </article>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const article = await $content('articles', params.slug).fetch()

    return { article }
  },

  computed: {
    meta() {
      const metaData = {
        type: 'article',
        title: this.article.title,
        description: this.article.description,
        url: `${this.$config.baseUrl}/articles/${this.$route.params.slug}`,
        mainImage: this.article.image,
      }
      return getSiteMeta(metaData)
    },
  },

  head() {
    return {
      title: this.article.title,
      meta: [
        ...this.meta,
        {
          property: 'article:published_time',
          content: this.article.createdAt,
        },
        {
          property: 'article:modified_time',
          content: this.article.updatedAt,
        },
        {
          property: 'article:tag',
          content: this.article.tags ? this.article.tags.toString() : '',
        },
        { name: 'twitter:label1', content: 'Written by' },
        {
          name: 'twitter:data1',
          content: this.article.author ? this.article.author.toString() : '',
        },
        { name: 'twitter:label2', content: 'Filed under' },
        {
          name: 'twitter:data2',
          content: this.article.tags ? this.article.tags.toString() : '',
        },
      ],
      link: [
        {
          hid: 'canonical',
          rel: 'canonical',
          href: `https://bobross.com/articles/${this.$route.params.slug}`,
        },
      ],
    }
  },
}
</script>

<style lang="scss">
#active_article {
  padding: 40px 15px;
  & h1 {
    padding: 20px 0;
  }
  & p {
    padding: 10px 0;
  }

  & a {
    font-style: italic;
  }
}
</style>
