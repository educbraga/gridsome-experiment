<template>
  <Layout>

    <!-- Learn how to use images here: https://gridsome.org/docs/images -->

    <h1>Hello, world!</h1>
    <div v-for="edge in $page.posts.edges" :key="edge.node.id">
      <p>{{ edge.node.name }}</p>
      <p>{{ edge.node.age }}</p>
      <p>{{ edge.node.date }}</p>
    </div>

    <p class="home-links">
      <a href="https://gridsome.org/docs/" target="_blank" rel="noopener">Gridsome Docs</a>
      <a href="https://github.com/gridsome/gridsome" target="_blank" rel="noopener">GitHub</a>
    </p>

  </Layout>
</template>
<page-query>
  query {
   posts: allGoogleSheet {
    edges {
      node {
        id
        name
        age
        date
      }
    }
  }
  }
</page-query>

<script>
export default {
  metaInfo: {
    title: 'Hello, world!'
  }
}
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>
