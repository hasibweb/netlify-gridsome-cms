<template>
    <Layout>    
        <h1>{{$page.post.title}}</h1>
        <sub>{{$page.post.excerpt}}</sub>
        <div v-html="$page.post.content" />
        
    </Layout>
</template>

<page-query>
query Post($path: String!) {
  post: posts(path: $path) {
    id
    title
    content
    title
    excerpt
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