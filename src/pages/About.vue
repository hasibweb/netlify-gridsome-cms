<template>
  <Layout>
    <h1>About us</h1>
    <div v-for="blog in blogs" :key="blog.node.content" v-html="blog.node.content" />
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Error doloremque omnis animi, eligendi magni a voluptatum, vitae, consequuntur rerum illum odit fugit assumenda rem dolores inventore iste reprehenderit maxime! Iusto.</p>
  </Layout>
</template>

<page-query>
query {
	posts: allBlogPost {
    edges {
      node {
        content
      }
    }
  }
}
</page-query>

<script>
export default {
  metaInfo: {
    title: 'About us'
  },
  computed: {
    blogs() {
      return this.$page.posts.edges
    }
  },
  mounted() {
    console.log(this.blogs)
  }
}
</script>
