<template>
  <Layout>
    <h1>Blog List</h1>

    <ol>
      <li v-for="post in $page.posts.edges" :key="post.node.id">
        <g-link :to="post.node.path">
          {{post.node.title}}
        </g-link>
      </li>
    </ol>
   
  </Layout>
</template>

<page-query>
query Posts {
  posts: allPosts {
    edges {
      node {
        id
        title
        path
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
