<template>
  <Layout>
    <h1>Hello, world!</h1>

    <p>
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Pariatur
      excepturi labore tempore expedita, et iste tenetur suscipit explicabo!
      Dolores, aperiam non officia eos quod asperiores
    </p>

    <ul class="list-item">
      <li v-for="post in $page.blogPosts.edges" :key="post.node.id">
        <g-link :to="post.node.path">{{ post.node.title }}</g-link>
      </li>
    </ul>
  </Layout>
</template>

<page-query>
query {
	blogPosts: allBlogPost {
    edges {
      node {        
        path
        excerpt
        id
        title
      }
    }
  }
}
</page-query>

<script>
export default {
  metaInfo: {
    title: "Hello, world!",
  },
};
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
.list-item li {
  display: block;
}
</style>
