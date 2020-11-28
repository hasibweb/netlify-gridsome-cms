<template>
    <Layout>
        Blog Template
        <div v-html="$page.post.content" ></div>
        
    </Layout>
</template>

<page-query>
query Post ($path: String!) {
 post: blogPost(path: $path) {
    content
    id
  }
}
</page-query>

<script>
    export default {
        
    }
</script>

<style>
    @import url("https://cdnjs.cloudflare.com/ajax/libs/github-markdown-css/4.0.0/github-markdown.min.css");
</style>